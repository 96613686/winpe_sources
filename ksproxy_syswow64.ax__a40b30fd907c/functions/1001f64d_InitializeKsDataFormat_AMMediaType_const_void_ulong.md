# InitializeKsDataFormat(_AMMediaType const *,void * *,ulong *)

- ea: `0x1001f64d`
- end: `0x1001f6e4`
- name: `?InitializeKsDataFormat@@YGJPBU_AMMediaType@@PAPAXPAK@Z`
- size: `151`
- prototype: `int __userpurge@<eax>(_DWORD *@<edx>, int@<ecx>, const struct _AMMediaType *, void **, unsigned int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1001b560`
- `0x1001c490`

## callees

- `0x1001f64d`
- `0x1003bcf8`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x1001f66a`
- `ole32!CoTaskMemAlloc` at `0x1001f66a`

## pseudocode

```c
int __userpurge InitializeKsDataFormat@<eax>(
        _DWORD *a1@<edx>,
        int a2@<ecx>,
        const struct _AMMediaType *a3,
        void **a4,
        unsigned int *a5)
{
  _DWORD *v7; // eax
  unsigned int v9; // [esp-4h] [ebp-10h]

  if ( *(_DWORD *)(a2 + 64) >= 0xFFFFFFC0 )
  {
    a3->majortype.Data1 = -1;
    return -2147024362;
  }
  else
  {
    v9 = *(_DWORD *)(a2 + 64) + 64;
    a3->majortype.Data1 = v9;
    v7 = CoTaskMemAlloc(v9);
    *a1 = v7;
    if ( v7 )
    {
      *v7 = *(_DWORD *)(a2 + 64) + 64;
      v7[1] = *(_DWORD *)(a2 + 36) != 0;
      v7[2] = *(_DWORD *)(a2 + 40);
      v7[3] = 0;
      v7[4] = *(_DWORD *)a2;
      v7[5] = *(_DWORD *)(a2 + 4);
      v7[6] = *(_DWORD *)(a2 + 8);
      v7[7] = *(_DWORD *)(a2 + 12);
      v7[8] = *(_DWORD *)(a2 + 16);
      v7[9] = *(_DWORD *)(a2 + 20);
      v7[10] = *(_DWORD *)(a2 + 24);
      v7[11] = *(_DWORD *)(a2 + 28);
      v7[12] = *(_DWORD *)(a2 + 44);
      v7[13] = *(_DWORD *)(a2 + 48);
      v7[14] = *(_DWORD *)(a2 + 52);
      v7[15] = *(_DWORD *)(a2 + 56);
      memcpy(v7 + 16, *(const void **)(a2 + 68), *(_DWORD *)(a2 + 64));
      return 0;
    }
    else
    {
      return -2147024882;
    }
  }
}

```

## disassembly

```asm
0x1001f64d  mov     edi, edi
0x1001f64f  push    ebp
0x1001f650  mov     ebp, esp
0x1001f652  push    ebx
0x1001f653  mov     ebx, ecx
0x1001f655  push    esi
0x1001f656  mov     esi, [ebp+arg_0]
0x1001f659  push    edi
0x1001f65a  mov     eax, [ebx+40h]
0x1001f65d  mov     edi, edx
0x1001f65f  add     eax, 40h ; '@'
0x1001f662  cmp     eax, 40h ; '@'
0x1001f665  jb      short loc_1001F6D2
0x1001f667  push    eax; cb
0x1001f668  mov     [esi], eax
0x1001f66a  call    ds:__imp__CoTaskMemAlloc@4; CoTaskMemAlloc(x)
0x1001f670  mov     ecx, eax
0x1001f672  mov     [edi], ecx
0x1001f674  test    ecx, ecx
0x1001f676  jnz     short loc_1001F67F
0x1001f678  mov     eax, 8007000Eh
0x1001f67d  jmp     short loc_1001F6DD
0x1001f67f  mov     eax, [ebx+40h]
0x1001f682  lea     edi, [ecx+10h]
0x1001f685  add     eax, 40h ; '@'
0x1001f688  mov     esi, ebx
0x1001f68a  mov     [ecx], eax
0x1001f68c  xor     eax, eax
0x1001f68e  cmp     [ebx+24h], eax
0x1001f691  setnz   al
0x1001f694  mov     [ecx+4], eax
0x1001f697  mov     eax, [ebx+28h]
0x1001f69a  mov     [ecx+8], eax
0x1001f69d  lea     eax, [ecx+40h]
0x1001f6a0  mov     dword ptr [ecx+0Ch], 0
0x1001f6a7  movsd
0x1001f6a8  movsd
0x1001f6a9  movsd
0x1001f6aa  movsd
0x1001f6ab  lea     edi, [ecx+20h]
0x1001f6ae  lea     esi, [ebx+10h]
0x1001f6b1  movsd
0x1001f6b2  movsd
0x1001f6b3  movsd
0x1001f6b4  movsd
0x1001f6b5  lea     edi, [ecx+30h]
0x1001f6b8  lea     esi, [ebx+2Ch]
0x1001f6bb  movsd
0x1001f6bc  movsd
0x1001f6bd  movsd
0x1001f6be  movsd
0x1001f6bf  push    dword ptr [ebx+40h]; Size
0x1001f6c2  push    dword ptr [ebx+44h]; Src
0x1001f6c5  push    eax; void *
0x1001f6c6  call    _memcpy
0x1001f6cb  add     esp, 0Ch
0x1001f6ce  xor     eax, eax
0x1001f6d0  jmp     short loc_1001F6DD
0x1001f6d2  mov     dword ptr [esi], 0FFFFFFFFh
0x1001f6d8  mov     eax, 80070216h
0x1001f6dd  pop     edi
0x1001f6de  pop     esi
0x1001f6df  pop     ebx
0x1001f6e0  pop     ebp
0x1001f6e1  retn    4
```
