# MFLightSensorReader::readOEMLevels(void)

- ea: `0x1800b28f0`
- end: `0x1800b2ada`
- name: `?readOEMLevels@MFLightSensorReader@@IEAAXXZ`
- size: `490`
- prototype: `void __fastcall(MFLightSensorReader *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800b1790`

## callees

- `0x18000c9d0`
- `0x18000ec20`
- `0x18000ecf0`
- `0x1800364d0`
- `0x180054140`
- `0x180066f48`
- `0x1800b28f0`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800b2a57`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800b2a57`

## string_xrefs

- `0x1800b29f9`: `OEMOutsideModeLuxLevels`
- `0x1800b2918`: `MFLightSensorReader::readOEMLevels`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall MFLightSensorReader::readOEMLevels(MFLightSensorReader *this)
{
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v3; // ebx
  _BYTE v4[4]; // [rsp+40h] [rbp-C0h] BYREF
  DWORD pcbData; // [rsp+44h] [rbp-BCh] BYREF
  _BYTE v6[16]; // [rsp+48h] [rbp-B8h] BYREF
  __int128 pvData; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR Value[28]; // [rsp+68h] [rbp-98h] BYREF
  WCHAR SubKey[56]; // [rsp+A0h] [rbp-60h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v4, "MFLightSensorReader::readOEMLevels", 157);
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 3) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v3 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 296LL))(*((_QWORD *)this + 3));
    *((_OWORD *)ThreadRelativeContext + 125) = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)this + 3) + 280LL))(
                                                            *((_QWORD *)this + 3),
                                                            v6);
    *((_DWORD *)ThreadRelativeContext + 504) = v3;
  }
  if ( g_wppLevels >= 8u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_4203d44df93a3264c8289945bccfb6ba_Traceguids, this);
  wcscpy(SubKey, L"Software\\Microsoft\\Windows Media Foundatiolatform");
  wcscpy(Value, L"OEMOutsideModeLuxLevels");
  pcbData = 16;
  if ( !RegGetValueW(HKEY_LOCAL_MACHINE, SubKey, Value, 8u, 0, &pvData, &pcbData) && pcbData == 16 )
  {
    if ( g_wppLevels >= 8u )
      WPP_SF_qdddd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        32,
        &WPP_4203d44df93a3264c8289945bccfb6ba_Traceguids,
        this,
        pvData,
        DWORD1(pvData),
        DWORD2(pvData),
        HIDWORD(pvData));
    *(_OWORD *)((char *)this + 60) = pvData;
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v4);
}

```

## disassembly

```asm
0x1800b28f0  push    rbp
0x1800b28f2  push    rbx
0x1800b28f3  push    rsi
0x1800b28f4  push    rdi
0x1800b28f5  lea     rbp, [rsp-28h]
0x1800b28fa  sub     rsp, 128h
0x1800b2901  mov     rax, cs:__security_cookie
0x1800b2908  xor     rax, rsp
0x1800b290b  mov     [rbp+40h+var_30], rax
0x1800b290f  mov     rsi, rcx
0x1800b2912  mov     r8d, 9Dh; int
0x1800b2918  lea     rdx, aMflightsensorr_0; "MFLightSensorReader::readOEMLevels"
0x1800b291f  lea     rcx, [rsp+140h+var_100]; this
0x1800b2924  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800b2929  nop
0x1800b292a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800b2931  cmp     byte ptr [rcx+8], 0
0x1800b2935  jz      short loc_1800B2984
0x1800b2937  cmp     qword ptr [rsi+18h], 0
0x1800b293c  jz      short loc_1800B2984
0x1800b293e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b2943  mov     rdi, rax
0x1800b2946  mov     rcx, [rsi+18h]
0x1800b294a  mov     rdx, [rcx]
0x1800b294d  mov     rax, [rdx+128h]
0x1800b2954  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b2959  mov     ebx, eax
0x1800b295b  mov     rcx, [rsi+18h]
0x1800b295f  mov     rdx, [rcx]
0x1800b2962  mov     rax, [rdx+118h]
0x1800b2969  lea     rdx, [rsp+140h+var_F8]
0x1800b296e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b2973  movups  xmm0, xmmword ptr [rax]
0x1800b2976  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x1800b297e  mov     [rdi+7E0h], ebx
0x1800b2984  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 8; MFWppLevels g_wppLevels
0x1800b298b  jb      short loc_1800B29AC
0x1800b298d  mov     edx, 1Fh
0x1800b2992  mov     r9, rsi
0x1800b2995  lea     r8, WPP_4203d44df93a3264c8289945bccfb6ba_Traceguids
0x1800b299c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b29a3  mov     rcx, [rcx+10h]
0x1800b29a7  call    WPP_SF_q
0x1800b29ac  movaps  xmm0, xmmword ptr cs:aSoftwareMicros_2; "Software\\Microsoft\\Windows Media Foun"...
0x1800b29b3  movaps  xmmword ptr [rbp+40h+SubKey], xmm0
0x1800b29b7  movaps  xmm1, xmmword ptr cs:aSoftwareMicros_2+10h; "\\Microsoft\\Windows Media Foundation\\"...
0x1800b29be  movaps  [rbp+40h+var_90], xmm1
0x1800b29c2  movaps  xmm0, xmmword ptr cs:aSoftwareMicros_2+20h; "ft\\Windows Media Foundation\\Platform"
0x1800b29c9  movaps  [rbp+40h+var_80], xmm0
0x1800b29cd  movaps  xmm1, xmmword ptr cs:aSoftwareMicros_2+30h; "ws Media Foundation\\Platform"
0x1800b29d4  movaps  [rbp+40h+var_70], xmm1
0x1800b29d8  movaps  xmm0, xmmword ptr cs:aSoftwareMicros_2+40h; " Foundation\\Platform"
0x1800b29df  movaps  [rbp+40h+var_60], xmm0
0x1800b29e3  movaps  xmm1, xmmword ptr cs:aSoftwareMicros_2+50h; "ion\\Platform"
0x1800b29ea  movaps  [rbp+40h+var_50], xmm1
0x1800b29ee  movups  xmm0, xmmword ptr cs:aSoftwareMicros_2+5Ah; "latform"
0x1800b29f5  movups  [rbp+40h+var_50+0Ah], xmm0
0x1800b29f9  movups  xmm1, xmmword ptr cs:aOemoutsidemode; "OEMOutsideModeLuxLevels"
0x1800b2a00  movups  xmmword ptr [rsp+140h+Value], xmm1
0x1800b2a05  movups  xmm0, xmmword ptr cs:aOemoutsidemode+10h; "deModeLuxLevels"
0x1800b2a0c  movups  [rsp+140h+var_C8], xmm0
0x1800b2a11  movups  xmm1, xmmword ptr cs:aOemoutsidemode+20h; "xLevels"
0x1800b2a18  movups  [rbp+40h+var_B8], xmm1
0x1800b2a1c  mov     [rsp+140h+var_FC], 10h
0x1800b2a24  lea     rax, [rsp+140h+var_FC]
0x1800b2a29  mov     [rsp+140h+pcbData], rax; pcbData
0x1800b2a2e  lea     rax, [rsp+140h+var_E8]
0x1800b2a33  mov     [rsp+140h+pvData], rax; pvData
0x1800b2a38  mov     [rsp+140h+pdwType], 0; pdwType
0x1800b2a41  mov     r9d, 8; dwFlags
0x1800b2a47  lea     r8, [rsp+140h+Value]; lpValue
0x1800b2a4c  lea     rdx, [rbp+40h+SubKey]; lpSubKey
0x1800b2a50  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800b2a57  call    cs:__imp_RegGetValueW
0x1800b2a5d  test    eax, eax
0x1800b2a5f  jnz     short loc_1800B2AB8
0x1800b2a61  cmp     [rsp+140h+var_FC], 10h
0x1800b2a66  jnz     short loc_1800B2AB8
0x1800b2a68  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 8; MFWppLevels g_wppLevels
0x1800b2a6f  jb      short loc_1800B2AAE
0x1800b2a71  lea     edx, [rax+20h]
0x1800b2a74  mov     eax, dword ptr [rsp+140h+var_E8+0Ch]
0x1800b2a78  mov     [rsp+140h+var_108], eax
0x1800b2a7c  mov     eax, dword ptr [rsp+140h+var_E8+8]
0x1800b2a80  mov     dword ptr [rsp+140h+pcbData], eax
0x1800b2a84  mov     eax, dword ptr [rsp+140h+var_E8+4]
0x1800b2a88  mov     dword ptr [rsp+140h+pvData], eax
0x1800b2a8c  mov     eax, dword ptr [rsp+140h+var_E8]
0x1800b2a90  mov     dword ptr [rsp+140h+pdwType], eax
0x1800b2a94  mov     r9, rsi
0x1800b2a97  lea     r8, WPP_4203d44df93a3264c8289945bccfb6ba_Traceguids
0x1800b2a9e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b2aa5  mov     rcx, [rcx+10h]
0x1800b2aa9  call    WPP_SF_qdddd
0x1800b2aae  movups  xmm0, [rsp+140h+var_E8]
0x1800b2ab3  movdqu  xmmword ptr [rsi+3Ch], xmm0
0x1800b2ab8  lea     rcx, [rsp+140h+var_100]; this
0x1800b2abd  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800b2ac2  mov     rcx, [rbp+40h+var_30]
0x1800b2ac6  xor     rcx, rsp; StackCookie
0x1800b2ac9  call    __security_check_cookie
0x1800b2ace  add     rsp, 128h
0x1800b2ad5  pop     rdi
0x1800b2ad6  pop     rsi
0x1800b2ad7  pop     rbx
0x1800b2ad8  pop     rbp
0x1800b2ad9  retn
```
