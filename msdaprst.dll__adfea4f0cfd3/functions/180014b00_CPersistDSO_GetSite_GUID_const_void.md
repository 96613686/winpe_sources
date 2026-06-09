# CPersistDSO::GetSite(_GUID const &,void * *)

- ea: `0x180014b00`
- end: `0x180014bc4`
- name: `?GetSite@CPersistDSO@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `196`
- prototype: `__int64 __fastcall(CPersistDSO *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180014b00`
- `0x18002a1d0`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180014b37`
- `KERNEL32!GetCurrentThreadId` at `0x180014b37`
- `KERNEL32!LeaveCriticalSection` at `0x180014ba2`
- `KERNEL32!LeaveCriticalSection` at `0x180014ba2`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180014b55`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180014b55`
- `MSDART!UMSEnterCSWraper` at `0x180014b25`
- `MSDART!UMSEnterCSWraper` at `0x180014b25`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CPersistDSO::GetSite(CPersistDSO *this, const struct _GUID *a2, void **a3)
{
  char *v6; // rbx
  unsigned int Site; // esi
  __int64 v9; // rcx

  v6 = (char *)this - 4488;
  UMSEnterCSWraper((char *)this - 4488);
  if ( !*((_DWORD *)v6 + 3) )
    *((_DWORD *)v6 + 2) = GetCurrentThreadId();
  ++*((_DWORD *)v6 + 3);
  ++*((_DWORD *)v6 + 4);
  SetErrorInfo(0, 0);
  *(GUID *)((char *)this - 4440) = IID_IObjectWithSite;
  *((_DWORD *)this - 81) = 0;
  Site = CImpIADOSecurity::GetSite(this, a2, a3);
  --*((_DWORD *)v6 + 4);
  if ( (*((_DWORD *)v6 + 3))-- == 1 )
    *((_DWORD *)v6 + 2) = -1;
  v9 = *(_QWORD *)v6;
  --*(_DWORD *)(v9 + 48);
  LeaveCriticalSection((LPCRITICAL_SECTION)(v9 + 8));
  return Site;
}

```

## disassembly

```asm
0x180014b00  mov     [rsp+arg_8], rbx
0x180014b05  mov     [rsp+arg_10], rbp
0x180014b0a  push    rsi
0x180014b0b  push    rdi
0x180014b0c  push    r14
0x180014b0e  sub     rsp, 20h
0x180014b12  mov     rbp, r8
0x180014b15  mov     r14, rdx
0x180014b18  mov     rsi, rcx
0x180014b1b  lea     rbx, [rcx-1188h]
0x180014b22  mov     rcx, rbx
0x180014b25  call    cs:__imp_UMSEnterCSWraper
0x180014b2c  nop     dword ptr [rax+rax+00h]
0x180014b31  cmp     dword ptr [rbx+0Ch], 0
0x180014b35  jnz     short loc_180014B46
0x180014b37  call    cs:__imp_GetCurrentThreadId
0x180014b3e  nop     dword ptr [rax+rax+00h]
0x180014b43  mov     [rbx+8], eax
0x180014b46  inc     dword ptr [rbx+0Ch]
0x180014b49  inc     dword ptr [rbx+10h]
0x180014b4c  mov     [rsp+38h+arg_0], rbx
0x180014b51  xor     edx, edx; perrinfo
0x180014b53  xor     ecx, ecx; dwReserved
0x180014b55  call    cs:__imp_SetErrorInfo
0x180014b5c  nop     dword ptr [rax+rax+00h]
0x180014b61  movups  xmm0, xmmword ptr cs:IID_IObjectWithSite.Data1
0x180014b68  movdqu  xmmword ptr [rsi-1158h], xmm0
0x180014b70  mov     dword ptr [rsi-144h], 0
0x180014b7a  mov     r8, rbp; void **
0x180014b7d  mov     rdx, r14; struct _GUID *
0x180014b80  mov     rcx, rsi; this
0x180014b83  call    ?GetSite@CImpIADOSecurity@@UEAAJAEBU_GUID@@PEAPEAX@Z; CImpIADOSecurity::GetSite(_GUID const &,void * *)
0x180014b88  mov     esi, eax
0x180014b8a  or      eax, 0FFFFFFFFh
0x180014b8d  add     [rbx+10h], eax
0x180014b90  add     [rbx+0Ch], eax
0x180014b93  jnz     short loc_180014B98
0x180014b95  mov     [rbx+8], eax
0x180014b98  mov     rcx, [rbx]
0x180014b9b  dec     dword ptr [rcx+30h]
0x180014b9e  add     rcx, 8; lpCriticalSection
0x180014ba2  call    cs:__imp_LeaveCriticalSection
0x180014ba9  nop     dword ptr [rax+rax+00h]
0x180014bae  mov     eax, esi
0x180014bb0  mov     rbx, [rsp+38h+arg_8]
0x180014bb5  mov     rbp, [rsp+38h+arg_10]
0x180014bba  add     rsp, 20h
0x180014bbe  pop     r14
0x180014bc0  pop     rdi
0x180014bc1  pop     rsi
0x180014bc2  retn
```
