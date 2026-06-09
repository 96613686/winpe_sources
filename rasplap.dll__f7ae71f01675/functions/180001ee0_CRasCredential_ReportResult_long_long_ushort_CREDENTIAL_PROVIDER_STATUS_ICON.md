# CRasCredential::ReportResult(long,long,ushort * *,_CREDENTIAL_PROVIDER_STATUS_ICON *)

- ea: `0x180001ee0`
- end: `0x18000210b`
- name: `?ReportResult@CRasCredential@@UEAAJJJPEAPEAGPEAW4_CREDENTIAL_PROVIDER_STATUS_ICON@@@Z`
- size: `555`
- prototype: `__int64 __usercall@<rax>(CRasCredential *__hidden this@<rcx>, int@<edx>, int@<r8d>, unsigned __int16 **@<r9>, enum _CREDENTIAL_PROVIDER_STATUS_ICON *)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, registry_config, installer_update`

## callees

- `0x180001ee0`
- `0x180002114`
- `0x1800028b8`
- `0x180004aa0`
- `0x180006144`
- `0x18000688c`
- `0x180006c58`
- `0x180007014`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18000207f`
- `KERNEL32!LocalFree` at `0x18000208e`
- `KERNEL32!LocalFree` at `0x18000209d`
- `KERNEL32!LocalFree` at `0x1800020ac`
- `KERNEL32!LocalFree` at `0x18000207f`
- `KERNEL32!LocalFree` at `0x18000208e`
- `KERNEL32!LocalFree` at `0x18000209d`
- `KERNEL32!LocalFree` at `0x1800020ac`
- `rtutils!TracePrintfExA` at `0x180001f20`
- `rtutils!TracePrintfExA` at `0x180002052`
- `rtutils!TracePrintfExA` at `0x180002071`
- `rtutils!TracePrintfExA` at `0x1800020cb`
- `rtutils!TracePrintfExA` at `0x180001f20`
- `rtutils!TracePrintfExA` at `0x180002052`
- `rtutils!TracePrintfExA` at `0x180002071`
- `rtutils!TracePrintfExA` at `0x1800020cb`

## string_xrefs

- `0x180002046`: `CRasCredential::ReportResult failed to update SC remove policy registry key : hr = %x`
- `0x180002065`: `CRasCredential::ReportResult failed to get scard readername.`

## pseudocode

```c
__int64 __fastcall CRasCredential::ReportResult(
        CRasCredential *this,
        int a2,
        int a3,
        unsigned __int16 **a4,
        enum _CREDENTIAL_PROVIDER_STATUS_ICON *a5)
{
  int v8; // ecx
  bool v9; // cf
  int ScardCertInfo; // eax
  _WORD *Src; // rbx
  __int64 v12; // rdx
  __int64 v13; // rcx
  int v14; // eax
  int v16; // [rsp+30h] [rbp-48h] BYREF
  HLOCAL v17; // [rsp+38h] [rbp-40h] BYREF
  struct _CRYPT_KEY_PROV_INFO v18; // [rsp+40h] [rbp-38h] BYREF
  HLOCAL hMem; // [rsp+C8h] [rbp+50h] BYREF

  if ( g_dwTraceId != -1 )
    TracePrintfExA(
      g_dwTraceId,
      0xCu,
      "CRasCredential::ReportResult called for [%S]: Status:0x%08X,SubStatus:0x%08X",
      (const wchar_t *)this + 10,
      a2,
      a3);
  hMem = 0;
  v17 = 0;
  v16 = 0;
  CRasCredential::_EraseFields(this);
  if ( a4 && a5 && !*((_DWORD *)this + 541) )
  {
    v8 = *((_DWORD *)this + 534);
    if ( *((_DWORD *)this + 138) != 1 )
      v8 = v8 == 0;
    if ( !*((_DWORD *)this + 533) )
    {
      if ( a2 >= 0 )
      {
        if ( !v8 )
          return 2147500033LL;
        v9 = *((_DWORD *)this + 535) != 0;
        memset(&v18, 0, sizeof(v18));
        ScardCertInfo = GetScardCertInfo(
                          (struct _CERT_HASH *)(((unsigned __int64)this + 2140) & -(__int64)v9),
                          (wchar_t **)&hMem,
                          (wchar_t **)&v17,
                          &v18);
        Src = hMem;
        if ( ScardCertInfo )
        {
          if ( !hMem )
          {
LABEL_24:
            if ( v17 )
              LocalFree(v17);
            if ( v18.pwszContainerName )
              LocalFree(v18.pwszContainerName);
            if ( v18.pwszProvName )
              LocalFree(v18.pwszProvName);
            return 2147500033LL;
          }
          if ( (int)GetScardReaderActivityCount((const WCHAR *)hMem, (DWORD *)&v16) >= 0 )
          {
            LODWORD(hMem) = 0;
            if ( !(unsigned int)ScPolicyGetPolicyOption(&hMem) )
            {
              if ( (_DWORD)hMem )
              {
                v14 = ScPolicyStoreLogonReaderInfo(v13, v12, NtCurrentPeb()->SessionId, v16, Src);
                if ( v14 > 0 )
                  v14 = (unsigned __int16)v14 | 0x80070000;
                if ( g_dwTraceId != -1 )
                  TracePrintfExA(
                    g_dwTraceId,
                    0xCu,
                    "CRasCredential::ReportResult failed to update SC remove policy registry key : hr = %x",
                    v14);
              }
            }
          }
        }
        else if ( g_dwTraceId != -1 )
        {
          TracePrintfExA(g_dwTraceId, 0xCu, "CRasCredential::ReportResult failed to get scard readername.");
        }
        if ( Src )
          LocalFree(Src);
        goto LABEL_24;
      }
      if ( g_dwTraceId != -1 )
        TracePrintfExA(
          g_dwTraceId,
          0xCu,
          "CRasCredential::ReportResult: Winlogon failed, hence disconnecting the RAS connection");
      if ( (int)RasDisconnect((wchar_t *)this + 10) >= 0 )
      {
        CRasCredential::_UpdateConnectStatus((const wchar_t *)this);
        *(_OWORD *)((char *)this + 2140) = 0;
        *(_QWORD *)((char *)this + 2156) = 0;
      }
    }
  }
  return 2147500033LL;
}

```

## disassembly

```asm
0x180001ee0  push    rbp
0x180001ee2  push    rbx
0x180001ee3  push    rsi
0x180001ee4  push    rdi
0x180001ee5  push    r12
0x180001ee7  push    r14
0x180001ee9  mov     rbp, rsp
0x180001eec  sub     rsp, 78h
0x180001ef0  mov     rbx, rcx
0x180001ef3  or      r12d, 0FFFFFFFFh
0x180001ef7  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180001efd  mov     r14, r9
0x180001f00  mov     esi, edx
0x180001f02  cmp     ecx, r12d
0x180001f05  jz      short loc_180001F26
0x180001f07  mov     [rsp+78h+var_50], r8d
0x180001f0c  lea     r9, [rbx+14h]
0x180001f10  mov     dword ptr [rsp+78h+Src], edx
0x180001f14  lea     r8, aCrascredential_21; "CRasCredential::ReportResult called for"...
0x180001f1b  mov     edx, 0Ch; dwFlags
0x180001f20  call    cs:__imp_TracePrintfExA
0x180001f26  mov     rcx, rbx; this
0x180001f29  mov     [rbp+hMem], 0
0x180001f31  mov     [rbp+var_40], 0
0x180001f39  mov     [rbp+var_48], 0
0x180001f40  call    ?_EraseFields@CRasCredential@@AEAAXXZ; CRasCredential::_EraseFields(void)
0x180001f45  test    r14, r14
0x180001f48  jz      loc_1800020F9
0x180001f4e  cmp     [rbp+arg_20], 0
0x180001f53  jz      loc_1800020F9
0x180001f59  cmp     dword ptr [rbx+874h], 0
0x180001f60  jnz     loc_1800020F9
0x180001f66  cmp     dword ptr [rbx+228h], 1
0x180001f6d  mov     ecx, [rbx+858h]
0x180001f73  jz      short loc_180001F7E
0x180001f75  xor     eax, eax
0x180001f77  test    ecx, ecx
0x180001f79  setz    al
0x180001f7c  mov     ecx, eax
0x180001f7e  cmp     dword ptr [rbx+854h], 0
0x180001f85  jnz     loc_1800020F9
0x180001f8b  test    esi, esi
0x180001f8d  js      loc_1800020B4
0x180001f93  test    ecx, ecx
0x180001f95  jz      loc_1800020F9
0x180001f9b  xorps   xmm0, xmm0
0x180001f9e  lea     rdx, [rbx+85Ch]
0x180001fa5  mov     eax, [rdx]
0x180001fa7  lea     r9, [rbp+var_38]
0x180001fab  neg     eax
0x180001fad  lea     r8, [rbp+var_40]
0x180001fb1  movups  xmmword ptr [rbp+var_38], xmm0
0x180001fb5  sbb     rcx, rcx
0x180001fb8  and     rcx, rdx
0x180001fbb  lea     rdx, [rbp+hMem]
0x180001fbf  movups  [rbp+var_28], xmm0
0x180001fc3  movups  [rbp+var_18], xmm0
0x180001fc7  call    GetScardCertInfo
0x180001fcc  mov     rbx, [rbp+hMem]
0x180001fd0  test    eax, eax
0x180001fd2  jz      loc_18000205A
0x180001fd8  test    rbx, rbx
0x180001fdb  jz      loc_180002085
0x180001fe1  lea     rdx, [rbp+var_48]
0x180001fe5  mov     rcx, rbx
0x180001fe8  call    GetScardReaderActivityCount
0x180001fed  test    eax, eax
0x180001fef  js      loc_180002077
0x180001ff5  lea     rcx, [rbp+hMem]
0x180001ff9  mov     dword ptr [rbp+hMem], 0
0x180002000  call    ScPolicyGetPolicyOption
0x180002005  test    eax, eax
0x180002007  jnz     short loc_180002077
0x180002009  cmp     dword ptr [rbp+hMem], eax
0x18000200c  jz      short loc_180002077
0x18000200e  mov     r8, gs:60h
0x180002017  mov     r9d, [rbp+var_48]; int
0x18000201b  mov     [rsp+78h+Src], rbx; Src
0x180002020  mov     r8d, [r8+2C0h]; int
0x180002027  call    ScPolicyStoreLogonReaderInfo
0x18000202c  test    eax, eax
0x18000202e  jle     short loc_180002038
0x180002030  movzx   eax, ax
0x180002033  or      eax, 80070000h
0x180002038  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18000203e  cmp     ecx, r12d
0x180002041  jz      short loc_180002077
0x180002043  mov     r9d, eax
0x180002046  lea     r8, aCrascredential_8; "CRasCredential::ReportResult failed to "...
0x18000204d  mov     edx, 0Ch; dwFlags
0x180002052  call    cs:__imp_TracePrintfExA
0x180002058  jmp     short loc_180002077
0x18000205a  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180002060  cmp     ecx, r12d
0x180002063  jz      short loc_180002077
0x180002065  lea     r8, aCrascredential_23; "CRasCredential::ReportResult failed to "...
0x18000206c  mov     edx, 0Ch; dwFlags
0x180002071  call    cs:__imp_TracePrintfExA
0x180002077  test    rbx, rbx
0x18000207a  jz      short loc_180002085
0x18000207c  mov     rcx, rbx; hMem
0x18000207f  call    cs:__imp_LocalFree
0x180002085  mov     rcx, [rbp+var_40]; hMem
0x180002089  test    rcx, rcx
0x18000208c  jz      short loc_180002094
0x18000208e  call    cs:__imp_LocalFree
0x180002094  mov     rcx, [rbp+var_38]; hMem
0x180002098  test    rcx, rcx
0x18000209b  jz      short loc_1800020A3
0x18000209d  call    cs:__imp_LocalFree
0x1800020a3  mov     rcx, [rbp+var_38+8]; hMem
0x1800020a7  test    rcx, rcx
0x1800020aa  jz      short loc_1800020F9
0x1800020ac  call    cs:__imp_LocalFree
0x1800020b2  jmp     short loc_1800020F9
0x1800020b4  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800020ba  cmp     ecx, r12d
0x1800020bd  jz      short loc_1800020D1
0x1800020bf  lea     r8, aCrascredential_10; "CRasCredential::ReportResult: Winlogon "...
0x1800020c6  mov     edx, 0Ch; dwFlags
0x1800020cb  call    cs:__imp_TracePrintfExA
0x1800020d1  lea     rcx, [rbx+14h]; String2
0x1800020d5  call    RasDisconnect
0x1800020da  test    eax, eax
0x1800020dc  js      short loc_1800020F9
0x1800020de  mov     rcx, rbx; this
0x1800020e1  call    ?_UpdateConnectStatus@CRasCredential@@AEAAXXZ; CRasCredential::_UpdateConnectStatus(void)
0x1800020e6  xorps   xmm0, xmm0
0x1800020e9  xor     eax, eax
0x1800020eb  movups  xmmword ptr [rbx+85Ch], xmm0
0x1800020f2  mov     [rbx+86Ch], rax
0x1800020f9  mov     eax, 80004001h
0x1800020fe  add     rsp, 78h
0x180002102  pop     r14
0x180002104  pop     r12
0x180002106  pop     rdi
0x180002107  pop     rsi
0x180002108  pop     rbx
0x180002109  pop     rbp
0x18000210a  retn
```
