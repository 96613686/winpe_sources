# AppGetCertSid(uchar const *,ulong,bool,wchar_t const *,ulong)

- ea: `0x180045c38`
- end: `0x180045d6d`
- name: `?AppGetCertSid@@YAPEAXPEBEK_NPEB_WK@Z`
- size: `309`
- prototype: `void *__fastcall(const unsigned __int8 *, unsigned int, bool, const wchar_t *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800b52c0`

## callees

- `0x18000f35c`
- `0x18000f430`
- `0x18002c61c`
- `0x18002c6c8`
- `0x180045c38`
- `0x180046a34`
- `0x18009bd1c`

## import_xrefs

- `msvcrt!free` at `0x180045d48`
- `msvcrt!free` at `0x180045d56`
- `msvcrt!free` at `0x180045d48`
- `msvcrt!free` at `0x180045d56`
- `ADVAPI32!CopySid` at `0x180045ce3`
- `ADVAPI32!CopySid` at `0x180045ce3`
- `ADVAPI32!GetLengthSid` at `0x180045cc3`
- `ADVAPI32!GetLengthSid` at `0x180045cc3`
- `KERNEL32!GetLastError` at `0x180045ced`
- `KERNEL32!GetLastError` at `0x180045ced`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void *__fastcall AppGetCertSid(const unsigned __int8 *a1, int a2, char a3, const wchar_t *a4, unsigned int a5)
{
  const wchar_t *v5; // rax
  unsigned int v6; // r9d
  int CertInfo_0; // eax
  __int64 v8; // rbx
  void *v10; // rcx
  DWORD LengthSid; // esi
  void *v12; // rdi
  DWORD LastError; // esi
  _QWORD v14[3]; // [rsp+30h] [rbp-18h] BYREF

  v5 = L"Microsoft Enhanced RSA and AES Cryptographic Provider";
  if ( !a3 )
    LODWORD(v5) = (_DWORD)a4;
  v6 = 24;
  if ( !a3 )
    v6 = a5;
  v14[0] = 0;
  CertInfo_0 = GetCertInfo_0((_DWORD)a1, a2, (_DWORD)v5, v6, 0, (__int64)v14);
  v8 = v14[0];
  if ( CertInfo_0 < 0 )
  {
    LogMsgHR(CertInfo_0, (wchar_t *)L"qmsecutl", 0x474u);
LABEL_7:
    SafeRelease<CSockTransport>(v8);
    return 0;
  }
  v10 = *(void **)(v14[0] + 32LL);
  if ( !v10 )
    goto LABEL_7;
  LengthSid = GetLengthSid(v10);
  v12 = MmAllocate(LengthSid);
  v14[1] = v12;
  if ( !CopySid(LengthSid, v12, *(PSID *)(v8 + 32)) )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 29, WPP_c687450366573ca356992ecf9dac13b8_Traceguids, LastError);
    if ( LastError )
      LogMsgNTStatus(LastError, (wchar_t *)L"qmsecutl", 0x475u);
    free(v12);
    goto LABEL_7;
  }
  free(0);
  SafeRelease<CSockTransport>(v8);
  return v12;
}

```

## disassembly

```asm
0x180045c38  mov     r11, rsp
0x180045c3b  mov     [r11+8], rbx
0x180045c3f  mov     [r11+10h], rsi
0x180045c43  push    rdi
0x180045c44  sub     rsp, 40h
0x180045c48  lea     rax, aMicrosoftEnhan; "Microsoft Enhanced RSA and AES Cryptogr"...
0x180045c4f  test    r8b, r8b
0x180045c52  cmovz   rax, r9
0x180045c56  mov     r9d, 18h
0x180045c5c  cmovz   r9d, [rsp+48h+arg_20]
0x180045c62  mov     qword ptr [r11-18h], 0
0x180045c6a  lea     r8, [r11-18h]
0x180045c6e  mov     [r11-20h], r8
0x180045c72  mov     [rsp+48h+var_28], 0
0x180045c7a  mov     r8, rax
0x180045c7d  call    GetCertInfo_0
0x180045c82  mov     rbx, [rsp+48h+var_18]
0x180045c87  test    eax, eax
0x180045c89  jns     short loc_180045CBA
0x180045c8b  mov     r8d, 474h; unsigned __int16
0x180045c91  lea     rdx, aQmsecutl; "qmsecutl"
0x180045c98  mov     ecx, eax; int
0x180045c9a  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180045c9f  nop
0x180045ca0  mov     rcx, rbx
0x180045ca3  call    ??$SafeRelease@VCSockTransport@@@@YAXPEAVCSockTransport@@@Z; SafeRelease<CSockTransport>(CSockTransport *)
0x180045ca8  xor     eax, eax
0x180045caa  mov     rbx, [rsp+48h+arg_0]
0x180045caf  mov     rsi, [rsp+48h+arg_8]
0x180045cb4  add     rsp, 40h
0x180045cb8  pop     rdi
0x180045cb9  retn
0x180045cba  mov     rcx, [rbx+20h]; pSid
0x180045cbe  test    rcx, rcx
0x180045cc1  jz      short loc_180045CA0
0x180045cc3  call    cs:__imp_GetLengthSid
0x180045cc9  mov     esi, eax
0x180045ccb  mov     ecx, eax; unsigned __int64
0x180045ccd  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x180045cd2  mov     rdi, rax
0x180045cd5  mov     [rsp+48h+var_10], rax
0x180045cda  mov     r8, [rbx+20h]; pSourceSid
0x180045cde  mov     rdx, rax; pDestinationSid
0x180045ce1  mov     ecx, esi; nDestinationSidLength
0x180045ce3  call    cs:__imp_CopySid
0x180045ce9  test    eax, eax
0x180045ceb  jnz     short loc_180045D54
0x180045ced  call    cs:__imp_GetLastError
0x180045cf3  mov     esi, eax
0x180045cf5  lea     rax, WPP_GLOBAL_Control
0x180045cfc  mov     rcx, cs:WPP_GLOBAL_Control
0x180045d03  cmp     rcx, rax
0x180045d06  jz      short loc_180045D2C
0x180045d08  test    byte ptr [rcx+10Ch], 1
0x180045d0f  jz      short loc_180045D2C
0x180045d11  mov     edx, 1Dh
0x180045d16  mov     r9d, esi
0x180045d19  lea     r8, WPP_c687450366573ca356992ecf9dac13b8_Traceguids
0x180045d20  mov     rcx, [rcx+100h]
0x180045d27  call    WPP_SF_d
0x180045d2c  test    esi, esi
0x180045d2e  jz      short loc_180045D45
0x180045d30  mov     r8d, 475h; unsigned __int16
0x180045d36  lea     rdx, aQmsecutl; "qmsecutl"
0x180045d3d  mov     ecx, esi; int
0x180045d3f  call    ?LogMsgNTStatus@@YAXJPEA_WG@Z; LogMsgNTStatus(long,wchar_t *,ushort)
0x180045d44  nop
0x180045d45  mov     rcx, rdi; Block
0x180045d48  call    cs:__imp_free
0x180045d4e  nop
0x180045d4f  jmp     loc_180045CA0
0x180045d54  xor     ecx, ecx; Block
0x180045d56  call    cs:__imp_free
0x180045d5c  nop
0x180045d5d  mov     rcx, rbx
0x180045d60  call    ??$SafeRelease@VCSockTransport@@@@YAXPEAVCSockTransport@@@Z; SafeRelease<CSockTransport>(CSockTransport *)
0x180045d65  mov     rax, rdi
0x180045d68  jmp     loc_180045CAA
```
