# CDDSYNCOBJECT::UpdateDxProcessInfo(uint,void * const *)

- ea: `0x14001c9e4`
- end: `0x14001cb58`
- name: `?UpdateDxProcessInfo@CDDSYNCOBJECT@@QEAAEIPEBQEAX@Z`
- size: `372`
- prototype: `unsigned __int8 __fastcall(CDDSYNCOBJECT *__hidden this, unsigned int, void *const *)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x14001c630`

## callees

- `0x140002130`
- `0x14001c9e4`
- `0x1400371f0`
- `0x1400372d0`
- `0x140037640`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x14001ca0e`
- `ntoskrnl!PsGetCurrentProcess` at `0x14001ca0e`
- `watchdog!WdLogSingleEntry2` at `0x14001cad0`
- `watchdog!WdLogSingleEntry2` at `0x14001cad0`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x14001cae7`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x14001cae7`

## pseudocode

```c
char __fastcall CDDSYNCOBJECT::UpdateDxProcessInfo(CDDSYNCOBJECT *this, __int64 a2, void *const *a3)
{
  unsigned int v4; // esi
  char v6; // di
  __int64 CurrentProcess; // rbp
  unsigned int v8; // ecx
  __int64 v9; // rax
  int v10; // edx
  int v11; // r8d
  __int64 v12; // rsi
  _QWORD *v13; // rax
  _DWORD v15[20]; // [rsp+20h] [rbp-98h] BYREF

  v4 = a2;
  v6 = 0;
  CurrentProcess = PsGetCurrentProcess(this, a2, a3);
  if ( v4 != *((_DWORD *)this + 6) )
  {
    *((_DWORD *)this + 6) = v4;
    v6 = 1;
    memset((char *)this + 28, 0, 0x104u);
  }
  v8 = 0;
  if ( v4 )
  {
    v9 = 0;
    do
    {
      v10 = (int)a3[v9];
      v11 = *((_DWORD *)this + v9 + 7);
      if ( v10 != v11 && v11 )
        v6 = 1;
      *((_DWORD *)this + v9 + 7) = v10;
      ++v8;
      ++v9;
    }
    while ( v8 < v4 );
  }
  if ( *((_QWORD *)this + 36) != CurrentProcess )
  {
    CDDSYNCOBJECT::DestroyDxSyncObject(this, 0);
    v12 = *(_QWORD *)(*((_QWORD *)this + 2) + 8LL);
    memset(v15, 0, 0x48u);
    v15[0] = *(_DWORD *)this;
    if ( (*(int (__fastcall **)(_DWORD *))(v12 + 384))(v15) < 0 )
    {
      WdLogSingleEntry2(4, v12, *((unsigned int *)this + 1));
      WdLogGlobalForLineNumber = 5920;
      v13 = (_QWORD *)WdLogNewEntry5_WdEvent();
      v13[3] = gCddImageInfo;
      v13[4] = (unsigned int)dword_14003E570;
      v13[5] = 215857758;
      WdLogGlobalForLineNumber = 5920;
      *((_DWORD *)this + 74) = 0;
    }
    else
    {
      *((_DWORD *)this + 74) = v15[1];
    }
    if ( *((_QWORD *)this + 36) )
      v6 = 1;
    *((_QWORD *)this + 36) = CurrentProcess;
  }
  return v6;
}

```

## disassembly

```asm
0x14001c9e4  push    rbx
0x14001c9e6  push    rbp
0x14001c9e7  push    rsi
0x14001c9e8  push    rdi
0x14001c9e9  push    r14
0x14001c9eb  push    r15
0x14001c9ed  sub     rsp, 88h
0x14001c9f4  mov     rax, cs:__security_cookie
0x14001c9fb  xor     rax, rsp
0x14001c9fe  mov     [rsp+0B8h+var_48], rax
0x14001ca03  mov     r14, r8
0x14001ca06  mov     esi, edx
0x14001ca08  mov     rbx, rcx
0x14001ca0b  xor     dil, dil
0x14001ca0e  call    cs:__imp_PsGetCurrentProcess
0x14001ca15  nop     dword ptr [rax+rax+00h]
0x14001ca1a  mov     r15d, 1
0x14001ca20  mov     rbp, rax
0x14001ca23  cmp     esi, [rbx+18h]
0x14001ca26  jz      short loc_14001CA3F
0x14001ca28  lea     rcx, [rbx+1Ch]; void *
0x14001ca2c  mov     [rbx+18h], esi
0x14001ca2f  xor     edx, edx; Val
0x14001ca31  mov     r8d, 104h; Size
0x14001ca37  mov     dil, r15b
0x14001ca3a  call    memset
0x14001ca3f  xor     ecx, ecx
0x14001ca41  test    esi, esi
0x14001ca43  jz      short loc_14001CA6E
0x14001ca45  xor     eax, eax
0x14001ca47  mov     edx, [r14+rax*8]
0x14001ca4b  mov     r8d, [rbx+rax*4+1Ch]
0x14001ca50  cmp     edx, r8d
0x14001ca53  jz      short loc_14001CA60
0x14001ca55  test    r8d, r8d
0x14001ca58  movzx   edi, dil
0x14001ca5c  cmovnz  edi, r15d
0x14001ca60  mov     [rbx+rax*4+1Ch], edx
0x14001ca64  add     ecx, r15d
0x14001ca67  add     rax, r15
0x14001ca6a  cmp     ecx, esi
0x14001ca6c  jb      short loc_14001CA47
0x14001ca6e  cmp     [rbx+120h], rbp
0x14001ca75  jz      loc_14001CB37
0x14001ca7b  xor     edx, edx; int
0x14001ca7d  mov     rcx, rbx; this
0x14001ca80  call    ?DestroyDxSyncObject@CDDSYNCOBJECT@@QEAAXH@Z; CDDSYNCOBJECT::DestroyDxSyncObject(int)
0x14001ca85  mov     rax, [rbx+10h]
0x14001ca89  lea     rcx, [rsp+0B8h+var_98]; void *
0x14001ca8e  xor     edx, edx; Val
0x14001ca90  mov     rsi, [rax+8]
0x14001ca94  lea     r8d, [rdx+48h]; Size
0x14001ca98  call    memset
0x14001ca9d  mov     eax, [rbx]
0x14001ca9f  lea     rcx, [rsp+0B8h+var_98]
0x14001caa4  mov     [rsp+0B8h+var_98], eax
0x14001caa8  mov     rax, [rsi+180h]
0x14001caaf  call    _guard_dispatch_icall
0x14001cab4  test    eax, eax
0x14001cab6  js      short loc_14001CAC4
0x14001cab8  mov     eax, [rsp+0B8h+var_94]
0x14001cabc  mov     [rbx+128h], eax
0x14001cac2  jmp     short loc_14001CB20
0x14001cac4  mov     r8d, [rbx+4]
0x14001cac8  mov     rdx, rsi
0x14001cacb  mov     ecx, 4
0x14001cad0  call    cs:__imp_WdLogSingleEntry2
0x14001cad7  nop     dword ptr [rax+rax+00h]
0x14001cadc  mov     esi, 1720h
0x14001cae1  mov     cs:WdLogGlobalForLineNumber, esi
0x14001cae7  call    cs:__imp_WdLogNewEntry5_WdEvent
0x14001caee  nop     dword ptr [rax+rax+00h]
0x14001caf3  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14001cafa  mov     [rax+18h], rcx
0x14001cafe  mov     ecx, cs:dword_14003E570
0x14001cb04  mov     [rax+20h], rcx
0x14001cb08  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x14001cb10  mov     cs:WdLogGlobalForLineNumber, esi
0x14001cb16  mov     dword ptr [rbx+128h], 0
0x14001cb20  cmp     qword ptr [rbx+120h], 0
0x14001cb28  movzx   edi, dil
0x14001cb2c  cmovnz  edi, r15d
0x14001cb30  mov     [rbx+120h], rbp
0x14001cb37  mov     al, dil
0x14001cb3a  mov     rcx, [rsp+0B8h+var_48]
0x14001cb3f  xor     rcx, rsp; StackCookie
0x14001cb42  call    __security_check_cookie
0x14001cb47  add     rsp, 88h
0x14001cb4e  pop     r15
0x14001cb50  pop     r14
0x14001cb52  pop     rdi
0x14001cb53  pop     rsi
0x14001cb54  pop     rbp
0x14001cb55  pop     rbx
0x14001cb56  retn
```
