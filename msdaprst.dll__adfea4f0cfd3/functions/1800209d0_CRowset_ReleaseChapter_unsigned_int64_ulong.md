# CRowset::ReleaseChapter(unsigned __int64,ulong *)

- ea: `0x1800209d0`
- end: `0x180020a71`
- name: `?ReleaseChapter@CRowset@@UEAAJ_KPEAK@Z`
- size: `161`
- prototype: `__int64 __fastcall(CRowset *__hidden this, unsigned __int64, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800209d0`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180020a06`
- `KERNEL32!GetCurrentThreadId` at `0x180020a06`
- `KERNEL32!LeaveCriticalSection` at `0x180020a58`
- `KERNEL32!LeaveCriticalSection` at `0x180020a58`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180020a24`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180020a24`
- `MSDART!UMSEnterCSWraper` at `0x1800209ea`
- `MSDART!UMSEnterCSWraper` at `0x1800209ea`

## pseudocode

```c
__int64 __fastcall CRowset::ReleaseChapter(CRowset *this, __int64 a2, unsigned int *a3)
{
  __int64 *v3; // r14
  DWORD *v6; // rdi
  __int64 v8; // rcx

  v3 = (__int64 *)((char *)this + 128);
  UMSEnterCSWraper((char *)this + 128);
  v6 = (DWORD *)((char *)this + 136);
  if ( !*((_DWORD *)this + 35) )
    *v6 = GetCurrentThreadId();
  ++*((_DWORD *)this + 35);
  ++*((_DWORD *)this + 36);
  SetErrorInfo(0, 0);
  if ( a3 )
    *a3 = 0;
  --*((_DWORD *)this + 36);
  if ( (*((_DWORD *)this + 35))-- == 1 )
    *v6 = -1;
  v8 = *v3;
  --*(_DWORD *)(v8 + 48);
  LeaveCriticalSection((LPCRITICAL_SECTION)(v8 + 8));
  return 0;
}

```

## disassembly

```asm
0x1800209d0  push    rbx
0x1800209d2  push    rsi
0x1800209d3  push    rdi
0x1800209d4  push    r14
0x1800209d6  sub     rsp, 28h
0x1800209da  lea     r14, [rcx+80h]
0x1800209e1  mov     rbx, rcx
0x1800209e4  mov     rcx, r14
0x1800209e7  mov     rsi, r8
0x1800209ea  call    cs:__imp_UMSEnterCSWraper
0x1800209f1  nop     dword ptr [rax+rax+00h]
0x1800209f6  cmp     dword ptr [rbx+8Ch], 0
0x1800209fd  lea     rdi, [rbx+88h]
0x180020a04  jnz     short loc_180020A14
0x180020a06  call    cs:__imp_GetCurrentThreadId
0x180020a0d  nop     dword ptr [rax+rax+00h]
0x180020a12  mov     [rdi], eax
0x180020a14  inc     dword ptr [rbx+8Ch]
0x180020a1a  xor     edx, edx; perrinfo
0x180020a1c  inc     dword ptr [rbx+90h]
0x180020a22  xor     ecx, ecx; dwReserved
0x180020a24  call    cs:__imp_SetErrorInfo
0x180020a2b  nop     dword ptr [rax+rax+00h]
0x180020a30  test    rsi, rsi
0x180020a33  jz      short loc_180020A3B
0x180020a35  mov     dword ptr [rsi], 0
0x180020a3b  or      ecx, 0FFFFFFFFh
0x180020a3e  add     [rbx+90h], ecx
0x180020a44  add     [rbx+8Ch], ecx
0x180020a4a  jnz     short loc_180020A4E
0x180020a4c  mov     [rdi], ecx
0x180020a4e  mov     rcx, [r14]
0x180020a51  dec     dword ptr [rcx+30h]
0x180020a54  add     rcx, 8; lpCriticalSection
0x180020a58  call    cs:__imp_LeaveCriticalSection
0x180020a5f  nop     dword ptr [rax+rax+00h]
0x180020a64  xor     eax, eax
0x180020a66  add     rsp, 28h
0x180020a6a  pop     r14
0x180020a6c  pop     rdi
0x180020a6d  pop     rsi
0x180020a6e  pop     rbx
0x180020a6f  retn
```
