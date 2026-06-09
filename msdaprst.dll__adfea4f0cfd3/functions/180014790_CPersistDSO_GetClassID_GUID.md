# CPersistDSO::GetClassID(_GUID *)

- ea: `0x180014790`
- end: `0x18001482d`
- name: `?GetClassID@CPersistDSO@@UEAAJPEAU_GUID@@@Z`
- size: `157`
- prototype: `__int64 __fastcall(CPersistDSO *__hidden this, struct _GUID *)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180014790`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800147b5`
- `KERNEL32!GetCurrentThreadId` at `0x1800147b5`
- `KERNEL32!LeaveCriticalSection` at `0x180014815`
- `KERNEL32!LeaveCriticalSection` at `0x180014815`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1800147ce`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1800147ce`
- `MSDART!UMSEnterCSWraper` at `0x1800147a3`
- `MSDART!UMSEnterCSWraper` at `0x1800147a3`

## pseudocode

```c
__int64 __fastcall CPersistDSO::GetClassID(CPersistDSO *this, struct _GUID *a2)
{
  __int64 v5; // rcx

  UMSEnterCSWraper((char *)this + 40);
  if ( !*((_DWORD *)this + 13) )
    *((_DWORD *)this + 12) = GetCurrentThreadId();
  ++*((_DWORD *)this + 13);
  ++*((_DWORD *)this + 14);
  SetErrorInfo(0, 0);
  *((_DWORD *)this + 1051) = 0;
  *(GUID *)((char *)this + 88) = IID_IPersist;
  *a2 = CLSID_MSPersist;
  --*((_DWORD *)this + 14);
  if ( (*((_DWORD *)this + 13))-- == 1 )
    *((_DWORD *)this + 12) = -1;
  v5 = *((_QWORD *)this + 5);
  --*(_DWORD *)(v5 + 48);
  LeaveCriticalSection((LPCRITICAL_SECTION)(v5 + 8));
  return 0;
}

```

## disassembly

```asm
0x180014790  push    rbx
0x180014792  push    rbp
0x180014793  push    rsi
0x180014794  push    rdi
0x180014795  sub     rsp, 28h
0x180014799  mov     rsi, rcx
0x18001479c  mov     rbp, rdx
0x18001479f  add     rcx, 28h ; '('
0x1800147a3  call    cs:__imp_UMSEnterCSWraper
0x1800147aa  nop     dword ptr [rax+rax+00h]
0x1800147af  cmp     dword ptr [rsi+34h], 0
0x1800147b3  jnz     short loc_1800147C4
0x1800147b5  call    cs:__imp_GetCurrentThreadId
0x1800147bc  nop     dword ptr [rax+rax+00h]
0x1800147c1  mov     [rsi+30h], eax
0x1800147c4  inc     dword ptr [rsi+34h]
0x1800147c7  xor     edx, edx; perrinfo
0x1800147c9  inc     dword ptr [rsi+38h]
0x1800147cc  xor     ecx, ecx; dwReserved
0x1800147ce  call    cs:__imp_SetErrorInfo
0x1800147d5  nop     dword ptr [rax+rax+00h]
0x1800147da  movups  xmm0, xmmword ptr cs:IID_IPersist.Data1
0x1800147e1  mov     dword ptr [rsi+106Ch], 0
0x1800147eb  or      ecx, 0FFFFFFFFh
0x1800147ee  movdqu  xmmword ptr [rsi+58h], xmm0
0x1800147f3  movups  xmm1, xmmword ptr cs:?CLSID_MSPersist@@3U_GUID@@B.Data1; _GUID const CLSID_MSPersist ...
0x1800147fa  movdqu  xmmword ptr [rbp+0], xmm1
0x1800147ff  add     [rsi+38h], ecx
0x180014802  add     [rsi+34h], ecx
0x180014805  jnz     short loc_18001480A
0x180014807  mov     [rsi+30h], ecx
0x18001480a  mov     rcx, [rsi+28h]
0x18001480e  dec     dword ptr [rcx+30h]
0x180014811  add     rcx, 8; lpCriticalSection
0x180014815  call    cs:__imp_LeaveCriticalSection
0x18001481c  nop     dword ptr [rax+rax+00h]
0x180014821  xor     eax, eax
0x180014823  add     rsp, 28h
0x180014827  pop     rdi
0x180014828  pop     rsi
0x180014829  pop     rbp
0x18001482a  pop     rbx
0x18001482b  retn
```
