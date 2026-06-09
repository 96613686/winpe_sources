# FwAuthApp::put_RemoteAddresses(ushort *)

- ea: `0x180044490`
- end: `0x180044751`
- name: `?put_RemoteAddresses@FwAuthApp@@UEAAJPEAG@Z`
- size: `705`
- prototype: `__int64 __fastcall(FwAuthApp *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x180001e3c`
- `0x18000283c`
- `0x1800294b0`
- `0x18002a1f4`
- `0x180044490`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800444fc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800444fc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800446ef`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800446ef`
- `fwbase!FwReportReturnError` at `0x1800446df`
- `fwbase!FwReportReturnError` at `0x180044719`
- `fwbase!FwReportReturnError` at `0x1800446df`
- `fwbase!FwReportReturnError` at `0x180044719`
- `FWPolicyIOMgr!StringToOpenPortOrAuthAppAddress` at `0x180044510`
- `FWPolicyIOMgr!StringToOpenPortOrAuthAppAddress` at `0x180044510`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x180044700`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x180044700`

## pseudocode

```c
__int64 __fastcall FwAuthApp::put_RemoteAddresses(FwAuthApp *this, unsigned __int16 *a2)
{
  int DefaultAuthAppRules; // eax
  int v5; // ebx
  _OWORD *v6; // rax
  _OWORD *v7; // rcx
  __int64 v8; // r8
  __int64 v9; // rdx
  __int128 v10; // xmm1
  _OWORD *v11; // rdx
  __int128 v12; // xmm2
  __int128 v13; // xmm3
  __int128 v14; // xmm4
  __int128 v15; // xmm5
  __int64 v16; // xmm6_8
  _OWORD *v17; // rax
  __int128 v18; // xmm1
  _OWORD v20[4]; // [rsp+28h] [rbp-E0h] BYREF
  __int64 v21; // [rsp+68h] [rbp-A0h]
  _BYTE v22[176]; // [rsp+78h] [rbp-90h] BYREF
  __int128 v23; // [rsp+128h] [rbp+20h]
  __int128 v24; // [rsp+138h] [rbp+30h]
  __int128 v25; // [rsp+148h] [rbp+40h]
  __int128 v26; // [rsp+158h] [rbp+50h]
  __int64 v27; // [rsp+168h] [rbp+60h]
  _BYTE v28[176]; // [rsp+278h] [rbp+170h] BYREF
  __int128 v29; // [rsp+328h] [rbp+220h]
  __int128 v30; // [rsp+338h] [rbp+230h]
  __int128 v31; // [rsp+348h] [rbp+240h]
  __int128 v32; // [rsp+358h] [rbp+250h]
  __int64 v33; // [rsp+368h] [rbp+260h]

  memset_0(v20, 0, 0x48u);
  memset_0(v28, 0, 0x1F8u);
  memset_0(v22, 0, 0x1F8u);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  DefaultAuthAppRules = StringToOpenPortOrAuthAppAddress(a2, v20);
  v5 = DefaultAuthAppRules;
  if ( DefaultAuthAppRules < 0 )
    goto LABEL_8;
  DefaultAuthAppRules = FwAuthApp::CreateDefaultAuthAppRules(this);
  v5 = DefaultAuthAppRules;
  if ( DefaultAuthAppRules < 0 )
    goto LABEL_8;
  v6 = (_OWORD *)*((_QWORD *)this + 9);
  v7 = v28;
  v8 = 3;
  v9 = 3;
  do
  {
    *v7 = *v6;
    v7[1] = v6[1];
    v7[2] = v6[2];
    v7[3] = v6[3];
    v7[4] = v6[4];
    v7[5] = v6[5];
    v7[6] = v6[6];
    v10 = v6[7];
    v6 += 8;
    v7[7] = v10;
    v7 += 8;
    --v9;
  }
  while ( v9 );
  v11 = v22;
  v12 = v20[0];
  v13 = v20[1];
  v14 = v20[2];
  v15 = v20[3];
  v16 = v21;
  *v7 = *v6;
  v7[1] = v6[1];
  v7[2] = v6[2];
  v7[3] = v6[3];
  v7[4] = v6[4];
  v7[5] = v6[5];
  v7[6] = v6[6];
  *((_QWORD *)v7 + 14) = *((_QWORD *)v6 + 14);
  v17 = (_OWORD *)*((_QWORD *)this + 10);
  v29 = v12;
  v30 = v13;
  v31 = v14;
  v32 = v15;
  v33 = v16;
  do
  {
    *v11 = *v17;
    v11[1] = v17[1];
    v11[2] = v17[2];
    v11[3] = v17[3];
    v11[4] = v17[4];
    v11[5] = v17[5];
    v11[6] = v17[6];
    v18 = v17[7];
    v17 += 8;
    v11[7] = v18;
    v11 += 8;
    --v8;
  }
  while ( v8 );
  *v11 = *v17;
  v11[1] = v17[1];
  v11[2] = v17[2];
  v11[3] = v17[3];
  v11[4] = v17[4];
  v11[5] = v17[5];
  v11[6] = v17[6];
  *((_QWORD *)v11 + 14) = *((_QWORD *)v17 + 14);
  v23 = v12;
  v24 = v13;
  v25 = v14;
  v26 = v15;
  v27 = v16;
  DefaultAuthAppRules = FwAuthApp::SetRules(this, (const struct _tag_FW_RULE *)v28, (const struct _tag_FW_RULE *)v22);
  v5 = DefaultAuthAppRules;
  if ( DefaultAuthAppRules < 0 )
LABEL_8:
    FwReportReturnError("FwAuthApp::put_RemoteAddresses", (unsigned int)DefaultAuthAppRules);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  FwPolioEmptyWFAddresses(v20);
  if ( v5 < 0 )
    return (unsigned int)FwReportReturnError("FwAuthApp::put_RemoteAddresses", (unsigned int)v5);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180044490  mov     rax, rsp
0x180044493  mov     [rax+18h], rbx
0x180044497  push    rbp
0x180044498  push    rsi
0x180044499  push    rdi
0x18004449a  lea     rbp, [rax-3A8h]
0x1800444a1  sub     rsp, 490h
0x1800444a8  movaps  xmmword ptr [rax-28h], xmm6
0x1800444ac  mov     rax, cs:__security_cookie
0x1800444b3  xor     rax, rsp
0x1800444b6  mov     [rbp+3A0h+var_30], rax
0x1800444bd  mov     rbx, rdx
0x1800444c0  mov     rdi, rcx
0x1800444c3  xor     edx, edx; Val
0x1800444c5  lea     rcx, [rsp+4A0h+var_488+8]; void *
0x1800444ca  lea     r8d, [rdx+48h]; Size
0x1800444ce  call    memset_0
0x1800444d3  mov     esi, 1F8h
0x1800444d8  lea     rcx, [rbp+3A0h+var_230]; void *
0x1800444df  mov     r8d, esi; Size
0x1800444e2  xor     edx, edx; Val
0x1800444e4  call    memset_0
0x1800444e9  mov     r8d, esi; Size
0x1800444ec  lea     rcx, [rsp+4A0h+var_430]; void *
0x1800444f1  xor     edx, edx; Val
0x1800444f3  call    memset_0
0x1800444f8  lea     rcx, [rdi+10h]; lpCriticalSection
0x1800444fc  call    cs:__imp_EnterCriticalSection
0x180044503  nop     dword ptr [rax+rax+00h]
0x180044508  lea     rdx, [rsp+4A0h+var_488+8]
0x18004450d  mov     rcx, rbx
0x180044510  call    cs:__imp_StringToOpenPortOrAuthAppAddress
0x180044517  nop     dword ptr [rax+rax+00h]
0x18004451c  mov     ebx, eax
0x18004451e  test    eax, eax
0x180044520  js      loc_1800446D6
0x180044526  mov     rcx, rdi; this
0x180044529  call    ?CreateDefaultAuthAppRules@FwAuthApp@@AEAAJXZ; FwAuthApp::CreateDefaultAuthAppRules(void)
0x18004452e  mov     ebx, eax
0x180044530  test    eax, eax
0x180044532  js      loc_1800446D6
0x180044538  mov     rax, [rdi+48h]
0x18004453c  lea     rcx, [rbp+3A0h+var_230]
0x180044543  mov     r8d, 3
0x180044549  mov     edx, r8d
0x18004454c  lea     r9d, [r8+7Dh]
0x180044550  movups  xmm0, xmmword ptr [rax]
0x180044553  movups  xmmword ptr [rcx], xmm0
0x180044556  movups  xmm1, xmmword ptr [rax+10h]
0x18004455a  movups  xmmword ptr [rcx+10h], xmm1
0x18004455e  movups  xmm0, xmmword ptr [rax+20h]
0x180044562  movups  xmmword ptr [rcx+20h], xmm0
0x180044566  movups  xmm1, xmmword ptr [rax+30h]
0x18004456a  movups  xmmword ptr [rcx+30h], xmm1
0x18004456e  movups  xmm0, xmmword ptr [rax+40h]
0x180044572  movups  xmmword ptr [rcx+40h], xmm0
0x180044576  movups  xmm1, xmmword ptr [rax+50h]
0x18004457a  movups  xmmword ptr [rcx+50h], xmm1
0x18004457e  movups  xmm0, xmmword ptr [rax+60h]
0x180044582  movups  xmmword ptr [rcx+60h], xmm0
0x180044586  movups  xmm1, xmmword ptr [rax+70h]
0x18004458a  add     rax, r9
0x18004458d  movups  xmmword ptr [rcx+70h], xmm1
0x180044591  add     rcx, r9
0x180044594  sub     rdx, 1
0x180044598  jnz     short loc_180044550
0x18004459a  movups  xmm0, xmmword ptr [rax]
0x18004459d  lea     rdx, [rsp+4A0h+var_430]
0x1800445a2  movaps  xmm2, [rsp+4A0h+var_488+8]
0x1800445a7  movaps  xmm3, [rsp+4A0h+var_478+8]
0x1800445ac  movaps  xmm4, [rsp+4A0h+var_468+8]
0x1800445b1  movaps  xmm5, [rsp+4A0h+var_458+8]
0x1800445b6  movsd   xmm6, [rsp+4A0h+var_440]
0x1800445bc  movups  xmmword ptr [rcx], xmm0
0x1800445bf  movups  xmm1, xmmword ptr [rax+10h]
0x1800445c3  movups  xmmword ptr [rcx+10h], xmm1
0x1800445c7  movups  xmm0, xmmword ptr [rax+20h]
0x1800445cb  movups  xmmword ptr [rcx+20h], xmm0
0x1800445cf  movups  xmm1, xmmword ptr [rax+30h]
0x1800445d3  movups  xmmword ptr [rcx+30h], xmm1
0x1800445d7  movups  xmm0, xmmword ptr [rax+40h]
0x1800445db  movups  xmmword ptr [rcx+40h], xmm0
0x1800445df  movups  xmm1, xmmword ptr [rax+50h]
0x1800445e3  movups  xmmword ptr [rcx+50h], xmm1
0x1800445e7  movups  xmm0, xmmword ptr [rax+60h]
0x1800445eb  movups  xmmword ptr [rcx+60h], xmm0
0x1800445ef  mov     rax, [rax+70h]
0x1800445f3  mov     [rcx+70h], rax
0x1800445f7  mov     rax, [rdi+50h]
0x1800445fb  movaps  [rbp+3A0h+var_180], xmm2
0x180044602  movaps  [rbp+3A0h+var_170], xmm3
0x180044609  movaps  [rbp+3A0h+var_160], xmm4
0x180044610  movaps  [rbp+3A0h+var_150], xmm5
0x180044617  movsd   [rbp+3A0h+var_140], xmm6
0x18004461f  movups  xmm0, xmmword ptr [rax]
0x180044622  movups  xmmword ptr [rdx], xmm0
0x180044625  movups  xmm1, xmmword ptr [rax+10h]
0x180044629  movups  xmmword ptr [rdx+10h], xmm1
0x18004462d  movups  xmm0, xmmword ptr [rax+20h]
0x180044631  movups  xmmword ptr [rdx+20h], xmm0
0x180044635  movups  xmm1, xmmword ptr [rax+30h]
0x180044639  movups  xmmword ptr [rdx+30h], xmm1
0x18004463d  movups  xmm0, xmmword ptr [rax+40h]
0x180044641  movups  xmmword ptr [rdx+40h], xmm0
0x180044645  movups  xmm1, xmmword ptr [rax+50h]
0x180044649  movups  xmmword ptr [rdx+50h], xmm1
0x18004464d  movups  xmm0, xmmword ptr [rax+60h]
0x180044651  movups  xmmword ptr [rdx+60h], xmm0
0x180044655  movups  xmm1, xmmword ptr [rax+70h]
0x180044659  add     rax, r9
0x18004465c  movups  xmmword ptr [rdx+70h], xmm1
0x180044660  add     rdx, r9
0x180044663  sub     r8, 1
0x180044667  jnz     short loc_18004461F
0x180044669  movups  xmm0, xmmword ptr [rax]
0x18004466c  lea     r8, [rsp+4A0h+var_430]; struct _tag_FW_RULE *
0x180044671  mov     rcx, rdi; this
0x180044674  movups  xmmword ptr [rdx], xmm0
0x180044677  movups  xmm1, xmmword ptr [rax+10h]
0x18004467b  movups  xmmword ptr [rdx+10h], xmm1
0x18004467f  movups  xmm0, xmmword ptr [rax+20h]
0x180044683  movups  xmmword ptr [rdx+20h], xmm0
0x180044687  movups  xmm1, xmmword ptr [rax+30h]
0x18004468b  movups  xmmword ptr [rdx+30h], xmm1
0x18004468f  movups  xmm0, xmmword ptr [rax+40h]
0x180044693  movups  xmmword ptr [rdx+40h], xmm0
0x180044697  movups  xmm1, xmmword ptr [rax+50h]
0x18004469b  movups  xmmword ptr [rdx+50h], xmm1
0x18004469f  movups  xmm0, xmmword ptr [rax+60h]
0x1800446a3  movups  xmmword ptr [rdx+60h], xmm0
0x1800446a7  mov     rax, [rax+70h]
0x1800446ab  mov     [rdx+70h], rax
0x1800446af  lea     rdx, [rbp+3A0h+var_230]; struct _tag_FW_RULE *
0x1800446b6  movaps  [rbp+3A0h+var_380], xmm2
0x1800446ba  movaps  [rbp+3A0h+var_370], xmm3
0x1800446be  movaps  [rbp+3A0h+var_360], xmm4
0x1800446c2  movaps  [rbp+3A0h+var_350], xmm5
0x1800446c6  movsd   [rbp+3A0h+var_340], xmm6
0x1800446cb  call    ?SetRules@FwAuthApp@@AEAAJPEBU_tag_FW_RULE@@0@Z; FwAuthApp::SetRules(_tag_FW_RULE const *,_tag_FW_RULE const *)
0x1800446d0  mov     ebx, eax
0x1800446d2  test    eax, eax
0x1800446d4  jns     short loc_1800446EB
0x1800446d6  mov     edx, eax
0x1800446d8  lea     rcx, aFwauthappPutRe; "FwAuthApp::put_RemoteAddresses"
0x1800446df  call    cs:__imp_FwReportReturnError
0x1800446e6  nop     dword ptr [rax+rax+00h]
0x1800446eb  lea     rcx, [rdi+10h]; lpCriticalSection
0x1800446ef  call    cs:__imp_LeaveCriticalSection
0x1800446f6  nop     dword ptr [rax+rax+00h]
0x1800446fb  lea     rcx, [rsp+4A0h+var_488+8]
0x180044700  call    cs:__imp_FwPolioEmptyWFAddresses
0x180044707  nop     dword ptr [rax+rax+00h]
0x18004470c  test    ebx, ebx
0x18004470e  jns     short loc_180044727
0x180044710  mov     edx, ebx
0x180044712  lea     rcx, aFwauthappPutRe; "FwAuthApp::put_RemoteAddresses"
0x180044719  call    cs:__imp_FwReportReturnError
0x180044720  nop     dword ptr [rax+rax+00h]
0x180044725  mov     ebx, eax
0x180044727  mov     eax, ebx
0x180044729  mov     rcx, [rbp+3A0h+var_30]
0x180044730  xor     rcx, rsp; StackCookie
0x180044733  call    __security_check_cookie
0x180044738  lea     r11, [rsp+4A0h+var_10]
0x180044740  mov     rbx, [r11+30h]
0x180044744  movaps  xmm6, xmmword ptr [r11-10h]
0x180044749  mov     rsp, r11
0x18004474c  pop     rdi
0x18004474d  pop     rsi
0x18004474e  pop     rbp
0x18004474f  retn
```
