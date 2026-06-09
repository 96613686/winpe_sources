# LsaDbpCheckTDODeletionQuotas(_LSAP_DB_HANDLE *)

- ea: `0x1800360f8`
- end: `0x1800361e6`
- name: `?LsaDbpCheckTDODeletionQuotas@@YAJPEAU_LSAP_DB_HANDLE@@@Z`
- size: `238`
- prototype: `__int64 __fastcall(struct _LSAP_DB_HANDLE *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180015bf0`

## callees

- `0x18001ff30`
- `0x180035fdc`
- `0x1800360f8`
- `0x1800361ec`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800361d5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800361d5`
- `LSASRV!LsapDbInitializeAttribute` at `0x180036132`
- `LSASRV!LsapDbInitializeAttribute` at `0x180036132`
- `LSASRV!LsapFreeLsaHeap` at `0x1800361c7`
- `LSASRV!LsapFreeLsaHeap` at `0x1800361c7`
- `ntdll!RtlEqualSid` at `0x1800361a6`
- `ntdll!RtlEqualSid` at `0x1800361a6`

## pseudocode

```c
__int64 __fastcall LsaDbpCheckTDODeletionQuotas(struct _UNICODE_STRING *a1)
{
  unsigned int v2; // edx
  int Attributes; // eax
  unsigned int v4; // ebx
  PSID v5; // rdi
  int CurrentOwnerAndPrimaryGroup; // eax
  __int64 v7; // rdx
  __int64 v8; // r8
  struct _TOKEN_OWNER *v9; // rsi
  PSID Owner; // rbp
  __int128 v12; // [rsp+30h] [rbp-58h] BYREF
  PSID Sid2[2]; // [rsp+40h] [rbp-48h]
  __int64 v14; // [rsp+50h] [rbp-38h]
  struct _TOKEN_OWNER *v15; // [rsp+90h] [rbp+8h] BYREF

  v15 = 0;
  v12 = 0;
  *(_OWORD *)Sid2 = 0;
  v14 = 0;
  LsapDbInitializeAttribute(&v12, 46, 0);
  v14 = *((_QWORD *)LsaDbpDsAttInfo + 69);
  Attributes = LsaDbpDsReadAttributes(a1 + 9, v2, (struct _LSAP_DB_ATTRIBUTE *)&v12, 1u);
  v4 = Attributes;
  if ( Attributes == -1073741275 )
  {
    return 0;
  }
  else if ( Attributes >= 0 )
  {
    v5 = Sid2[0];
    CurrentOwnerAndPrimaryGroup = LsaDbpGetCurrentOwnerAndPrimaryGroup(&v15, 0);
    v9 = v15;
    v4 = CurrentOwnerAndPrimaryGroup;
    if ( CurrentOwnerAndPrimaryGroup >= 0 )
    {
      Owner = v15->Owner;
      if ( RtlEqualSid(v15->Owner, v5) )
        v4 = LsaDbpCheckDelegatedTDOQuotas(Owner, 4u);
    }
    if ( v9 )
      LsapFreeLsaHeap(v9, v7, v8);
    if ( v5 )
      LocalFree(v5);
  }
  return v4;
}

```

## disassembly

```asm
0x1800360f8  mov     r11, rsp
0x1800360fb  push    rbx
0x1800360fc  push    rbp
0x1800360fd  push    rsi
0x1800360fe  push    rdi
0x1800360ff  sub     rsp, 68h
0x180036103  xor     eax, eax
0x180036105  mov     qword ptr [r11+8], 0
0x18003610d  xorps   xmm0, xmm0
0x180036110  mov     [rsp+88h+var_68], al
0x180036114  mov     rbx, rcx
0x180036117  xor     r9d, r9d
0x18003611a  movups  [rsp+88h+var_58], xmm0
0x18003611f  lea     edx, [rax+2Eh]
0x180036122  xor     r8d, r8d
0x180036125  movups  xmmword ptr [rsp+88h+Sid2], xmm0
0x18003612a  lea     rcx, [r11-58h]
0x18003612e  mov     [r11-38h], rax
0x180036132  call    cs:__imp_LsapDbInitializeAttribute
0x180036138  mov     rcx, cs:?LsaDbpDsAttInfo@@3PEAU_LSAP_DB_DS_INFO@@EA; _LSAP_DB_DS_INFO * LsaDbpDsAttInfo
0x18003613f  lea     r8, [rsp+88h+var_58]; struct _LSAP_DB_ATTRIBUTE *
0x180036144  mov     r9d, 1; unsigned int
0x18003614a  mov     eax, [rcx+228h]
0x180036150  mov     [rsp+88h+var_38], eax
0x180036154  mov     eax, [rcx+22Ch]
0x18003615a  lea     rcx, [rbx+90h]; struct _UNICODE_STRING *
0x180036161  mov     [rsp+88h+var_34], eax
0x180036165  call    ?LsaDbpDsReadAttributes@@YAJPEAU_UNICODE_STRING@@KPEAU_LSAP_DB_ATTRIBUTE@@K@Z; LsaDbpDsReadAttributes(_UNICODE_STRING *,ulong,_LSAP_DB_ATTRIBUTE *,ulong)
0x18003616a  mov     ebx, eax
0x18003616c  cmp     eax, 0C0000225h
0x180036171  jnz     short loc_180036177
0x180036173  xor     ebx, ebx
0x180036175  jmp     short loc_1800361DB
0x180036177  test    eax, eax
0x180036179  js      short loc_1800361DB
0x18003617b  mov     rdi, [rsp+88h+Sid2]
0x180036180  lea     rcx, [rsp+88h+arg_0]; struct _TOKEN_OWNER **
0x180036188  xor     edx, edx; struct _TOKEN_PRIMARY_GROUP **
0x18003618a  call    ?LsaDbpGetCurrentOwnerAndPrimaryGroup@@YAJPEAPEAU_TOKEN_OWNER@@PEAPEAU_TOKEN_PRIMARY_GROUP@@@Z; LsaDbpGetCurrentOwnerAndPrimaryGroup(_TOKEN_OWNER * *,_TOKEN_PRIMARY_GROUP * *)
0x18003618f  mov     rsi, [rsp+88h+arg_0]
0x180036197  mov     ebx, eax
0x180036199  test    eax, eax
0x18003619b  js      short loc_1800361BF
0x18003619d  mov     rbp, [rsi]
0x1800361a0  mov     rdx, rdi; Sid2
0x1800361a3  mov     rcx, rbp; Sid1
0x1800361a6  call    cs:__imp_RtlEqualSid
0x1800361ac  test    al, al
0x1800361ae  jz      short loc_1800361BF
0x1800361b0  mov     edx, 4; unsigned int
0x1800361b5  mov     rcx, rbp; void *
0x1800361b8  call    ?LsaDbpCheckDelegatedTDOQuotas@@YAJPEAXK@Z; LsaDbpCheckDelegatedTDOQuotas(void *,ulong)
0x1800361bd  mov     ebx, eax
0x1800361bf  test    rsi, rsi
0x1800361c2  jz      short loc_1800361CD
0x1800361c4  mov     rcx, rsi
0x1800361c7  call    cs:__imp_LsapFreeLsaHeap
0x1800361cd  test    rdi, rdi
0x1800361d0  jz      short loc_1800361DB
0x1800361d2  mov     rcx, rdi; hMem
0x1800361d5  call    cs:__imp_LocalFree
0x1800361db  mov     eax, ebx
0x1800361dd  add     rsp, 68h
0x1800361e1  pop     rdi
0x1800361e2  pop     rsi
0x1800361e3  pop     rbp
0x1800361e4  pop     rbx
0x1800361e5  retn
```
