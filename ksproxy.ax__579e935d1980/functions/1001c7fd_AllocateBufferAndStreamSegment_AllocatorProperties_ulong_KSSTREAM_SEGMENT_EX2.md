# AllocateBufferAndStreamSegment(_AllocatorProperties *,ulong,_KSSTREAM_SEGMENT_EX2 * *)

- ea: `0x1001c7fd`
- end: `0x1001c910`
- name: `?AllocateBufferAndStreamSegment@@YGJPAU_AllocatorProperties@@KPAPAU_KSSTREAM_SEGMENT_EX2@@@Z`
- size: `275`
- prototype: `int __stdcall(struct _AllocatorProperties *, unsigned int, struct _KSSTREAM_SEGMENT_EX2 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x1001d103`

## callees

- `0x1001c7fd`
- `0x1003a6f2`
- `0x1003a6fd`
- `0x1003a72c`
- `0x1003af9d`
- `0x1003b5e4`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x1001c852`
- `KERNEL32!CreateEventW` at `0x1001c852`
- `KERNEL32!CloseHandle` at `0x1001c8c5`
- `KERNEL32!CloseHandle` at `0x1001c8c5`

## pseudocode

```c
int __userpurge AllocateBufferAndStreamSegment@<eax>(
        int a1@<edx>,
        int a2@<ecx>,
        struct _AllocatorProperties *a3,
        unsigned int a4,
        struct _KSSTREAM_SEGMENT_EX2 **a5)
{
  int v6; // edi
  _DWORD *v7; // esi
  _DWORD *v8; // ebx
  void *v9; // eax
  HANDLE hObject; // [esp+Ch] [ebp-Ch]

  v6 = 0;
  v7 = operator new(0x138u);
  if ( !v7 )
    return -2147024882;
  v8 = operator new[](a1 + 48);
  if ( !v8 )
  {
    operator delete(v7, 0x138u);
    return -2147024882;
  }
  hObject = CreateEventW(0, 0, 0, 0);
  if ( hObject )
  {
    memset(v7, 0, 0x138u);
    memset(v8, 0, a1 + 48);
    v9 = operator new[](*(_DWORD *)(a2 + 4));
    if ( v9 )
    {
      v8[10] = v9;
      *v8 = a1 + 48;
      v8[8] = *(_DWORD *)(a2 + 4);
      v7[69] = a1;
      v7[70] = v8;
      v7[4] = 0;
      v7[68] = 0;
      v7[75] = hObject;
      v7[3] = hObject;
      a3->cBuffers = (int)v7;
    }
    else
    {
      v6 = -2147024882;
      operator delete(v7, 0x138u);
      operator delete[](v8);
      CloseHandle(hObject);
    }
  }
  else
  {
    operator delete(v7, 0x138u);
    operator delete[](v8);
    return -2147467259;
  }
  return v6;
}

```

## disassembly

```asm
0x1001c7fd  mov     edi, edi
0x1001c7ff  push    ebp
0x1001c800  mov     ebp, esp
0x1001c802  sub     esp, 0Ch
0x1001c805  push    ebx
0x1001c806  push    esi
0x1001c807  push    edi
0x1001c808  mov     ebx, edx
0x1001c80a  mov     [ebp+var_8], ecx
0x1001c80d  push    138h; Size
0x1001c812  mov     [ebp+var_4], ebx
0x1001c815  xor     edi, edi
0x1001c817  call    ??2@YAPAXI@Z; operator new(uint)
0x1001c81c  mov     esi, eax
0x1001c81e  pop     ecx
0x1001c81f  test    esi, esi
0x1001c821  jnz     short loc_1001C82D
0x1001c823  mov     edi, 8007000Eh
0x1001c828  jmp     loc_1001C907
0x1001c82d  lea     eax, [ebx+30h]
0x1001c830  push    eax; unsigned int
0x1001c831  call    ??_U@YAPAXI@Z; operator new[](uint)
0x1001c836  mov     ebx, eax
0x1001c838  pop     ecx
0x1001c839  test    ebx, ebx
0x1001c83b  jnz     short loc_1001C84C
0x1001c83d  push    138h; unsigned int
0x1001c842  push    esi; Block
0x1001c843  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x1001c848  pop     ecx
0x1001c849  pop     ecx
0x1001c84a  jmp     short loc_1001C823
0x1001c84c  xor     eax, eax
0x1001c84e  push    eax; lpName
0x1001c84f  push    eax; bInitialState
0x1001c850  push    eax; bManualReset
0x1001c851  push    eax; lpEventAttributes
0x1001c852  call    ds:__imp__CreateEventW@16; CreateEventW(x,x,x,x)
0x1001c858  mov     [ebp+hObject], eax
0x1001c85b  push    138h; unsigned int
0x1001c860  test    eax, eax
0x1001c862  jnz     short loc_1001C87D
0x1001c864  push    esi; Block
0x1001c865  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x1001c86a  push    ebx; Block
0x1001c86b  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1001c870  add     esp, 0Ch
0x1001c873  mov     edi, 80004005h
0x1001c878  jmp     loc_1001C907
0x1001c87d  push    0; Val
0x1001c87f  push    esi; void *
0x1001c880  call    _memset
0x1001c885  mov     eax, [ebp+var_4]
0x1001c888  add     eax, 30h ; '0'
0x1001c88b  push    eax; Size
0x1001c88c  push    0; Val
0x1001c88e  push    ebx; void *
0x1001c88f  call    _memset
0x1001c894  mov     eax, [ebp+var_8]
0x1001c897  push    dword ptr [eax+4]; unsigned int
0x1001c89a  call    ??_U@YAPAXI@Z; operator new[](uint)
0x1001c89f  mov     edx, eax
0x1001c8a1  add     esp, 1Ch
0x1001c8a4  test    edx, edx
0x1001c8a6  jnz     short loc_1001C8CD
0x1001c8a8  push    138h; unsigned int
0x1001c8ad  push    esi; Block
0x1001c8ae  mov     edi, 8007000Eh
0x1001c8b3  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x1001c8b8  push    ebx; Block
0x1001c8b9  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1001c8be  mov     eax, [ebp+hObject]
0x1001c8c1  add     esp, 0Ch
0x1001c8c4  push    eax; hObject
0x1001c8c5  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x1001c8cb  jmp     short loc_1001C907
0x1001c8cd  mov     ecx, [ebp+var_4]
0x1001c8d0  mov     [ebx+28h], edx
0x1001c8d3  lea     eax, [ecx+30h]
0x1001c8d6  mov     [ebx], eax
0x1001c8d8  mov     eax, [ebp+var_8]
0x1001c8db  mov     eax, [eax+4]
0x1001c8de  mov     [ebx+20h], eax
0x1001c8e1  mov     eax, [ebp+hObject]
0x1001c8e4  mov     [esi+114h], ecx
0x1001c8ea  mov     ecx, [ebp+arg_0]
0x1001c8ed  mov     [esi+118h], ebx
0x1001c8f3  mov     [esi+10h], edi
0x1001c8f6  mov     [esi+110h], edi
0x1001c8fc  mov     [esi+12Ch], eax
0x1001c902  mov     [esi+0Ch], eax
0x1001c905  mov     [ecx], esi
0x1001c907  mov     eax, edi
0x1001c909  pop     edi
0x1001c90a  pop     esi
0x1001c90b  pop     ebx
0x1001c90c  leave
0x1001c90d  retn    4
```
