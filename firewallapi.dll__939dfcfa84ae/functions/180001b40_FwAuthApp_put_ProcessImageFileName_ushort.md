# FwAuthApp::put_ProcessImageFileName(ushort *)

- ea: `0x180001b40`
- end: `0x180001e35`
- name: `?put_ProcessImageFileName@FwAuthApp@@UEAAJPEAG@Z`
- size: `757`
- prototype: `__int64 __fastcall(FwAuthApp *__hidden this, BSTR pbstr)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180001b40`
- `0x180001e3c`
- `0x18000283c`
- `0x1800294b0`
- `0x18002a1f4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001bb8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001bb8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001dc6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001dc6`
- `OLEAUT32!__imp_SysStringLen` at `0x180001bc7`
- `OLEAUT32!__imp_SysStringLen` at `0x180001bc7`
- `fwbase!FwBaseFree` at `0x180001de8`
- `fwbase!FwBaseFree` at `0x180001de8`
- `fwbase!FwImageListDestroy` at `0x180001dd7`
- `fwbase!FwImageListDestroy` at `0x180001dd7`
- `fwbase!FwImageListHasImage` at `0x180001c2d`
- `fwbase!FwImageListHasImage` at `0x180001c2d`
- `fwbase!FwGetAppBlockList` at `0x180001c0d`
- `fwbase!FwGetAppBlockList` at `0x180001c0d`
- `fwbase!FwGetSysPathName` at `0x180001bf2`
- `fwbase!FwGetSysPathName` at `0x180001bf2`
- `fwbase!FwReportReturnError` at `0x180001db6`
- `fwbase!FwReportReturnError` at `0x180001dfd`
- `fwbase!FwReportReturnError` at `0x180001db6`
- `fwbase!FwReportReturnError` at `0x180001dfd`

## pseudocode

```c
__int64 __fastcall FwAuthApp::put_ProcessImageFileName(FwAuthApp *this, BSTR pbstr)
{
  unsigned int v4; // ebx
  __int64 v5; // rdx
  int SysPathName; // eax
  _OWORD *v7; // rax
  _OWORD *v8; // rcx
  __int64 v9; // r8
  __int64 v10; // rdx
  __int128 v11; // xmm1
  __int64 v12; // r9
  _OWORD *v13; // rdx
  _OWORD *v14; // rax
  __int128 v15; // xmm1
  __int64 v17; // [rsp+20h] [rbp-E0h] BYREF
  _QWORD v18[3]; // [rsp+28h] [rbp-D8h] BYREF
  _BYTE v19[272]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v20; // [rsp+150h] [rbp+50h]
  _BYTE v21[272]; // [rsp+240h] [rbp+140h] BYREF
  __int64 v22; // [rsp+350h] [rbp+250h]

  v17 = 0;
  v18[0] = 0;
  v18[1] = 0;
  memset_0(v21, 0, 0x1F8u);
  memset_0(v19, 0, 0x1F8u);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( !SysStringLen(pbstr) )
  {
    v4 = -2147024809;
LABEL_3:
    v5 = v4;
LABEL_15:
    FwReportReturnError("FwAuthApp::put_ProcessImageFileName", v5);
    goto LABEL_16;
  }
  SysPathName = FwGetSysPathName(pbstr, &v17);
  v4 = SysPathName;
  if ( SysPathName < 0 )
    goto LABEL_14;
  SysPathName = FwGetAppBlockList(v18);
  v4 = SysPathName;
  if ( SysPathName < 0 )
    goto LABEL_14;
  if ( (unsigned int)FwImageListHasImage(v18, v17) )
  {
    v4 = -2147016473;
    goto LABEL_3;
  }
  SysPathName = FwAuthApp::CreateDefaultAuthAppRules(this);
  v4 = SysPathName;
  if ( SysPathName < 0 )
    goto LABEL_14;
  v7 = (_OWORD *)*((_QWORD *)this + 9);
  v8 = v21;
  v9 = 3;
  v10 = 3;
  do
  {
    *v8 = *v7;
    v8[1] = v7[1];
    v8[2] = v7[2];
    v8[3] = v7[3];
    v8[4] = v7[4];
    v8[5] = v7[5];
    v8[6] = v7[6];
    v11 = v7[7];
    v7 += 8;
    v8[7] = v11;
    v8 += 8;
    --v10;
  }
  while ( v10 );
  v12 = v17;
  v13 = v19;
  *v8 = *v7;
  v8[1] = v7[1];
  v8[2] = v7[2];
  v8[3] = v7[3];
  v8[4] = v7[4];
  v8[5] = v7[5];
  v8[6] = v7[6];
  *((_QWORD *)v8 + 14) = *((_QWORD *)v7 + 14);
  v14 = (_OWORD *)*((_QWORD *)this + 10);
  v22 = v12;
  do
  {
    *v13 = *v14;
    v13[1] = v14[1];
    v13[2] = v14[2];
    v13[3] = v14[3];
    v13[4] = v14[4];
    v13[5] = v14[5];
    v13[6] = v14[6];
    v15 = v14[7];
    v14 += 8;
    v13[7] = v15;
    v13 += 8;
    --v9;
  }
  while ( v9 );
  *v13 = *v14;
  v13[1] = v14[1];
  v13[2] = v14[2];
  v13[3] = v14[3];
  v13[4] = v14[4];
  v13[5] = v14[5];
  v13[6] = v14[6];
  *((_QWORD *)v13 + 14) = *((_QWORD *)v14 + 14);
  v20 = v12;
  SysPathName = FwAuthApp::SetRules(this, (const struct _tag_FW_RULE *)v21, (const struct _tag_FW_RULE *)v19);
  v4 = SysPathName;
  if ( SysPathName < 0 )
  {
LABEL_14:
    v5 = (unsigned int)SysPathName;
    goto LABEL_15;
  }
LABEL_16:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  FwImageListDestroy(v18);
  FwBaseFree(v17);
  if ( (v4 & 0x80000000) != 0 )
    return (unsigned int)FwReportReturnError("FwAuthApp::put_ProcessImageFileName", v4);
  return v4;
}

```

## disassembly

```asm
0x180001b40  mov     [rsp-8+arg_10], rbx
0x180001b45  mov     [rsp-8+arg_18], rsi
0x180001b4a  push    rbp
0x180001b4b  push    rdi
0x180001b4c  push    r14
0x180001b4e  lea     rbp, [rsp-350h]
0x180001b56  sub     rsp, 450h
0x180001b5d  mov     rax, cs:__security_cookie
0x180001b64  xor     rax, rsp
0x180001b67  mov     [rbp+360h+var_20], rax
0x180001b6e  mov     rbx, rdx
0x180001b71  mov     [rsp+460h+var_440], 0
0x180001b7a  mov     rdi, rcx
0x180001b7d  mov     [rsp+460h+var_438], 0
0x180001b86  mov     esi, 1F8h
0x180001b8b  mov     [rsp+460h+var_430], 0
0x180001b94  mov     r8d, esi; Size
0x180001b97  lea     rcx, [rbp+360h+var_220]; void *
0x180001b9e  xor     edx, edx; Val
0x180001ba0  call    memset_0
0x180001ba5  mov     r8d, esi; Size
0x180001ba8  lea     rcx, [rsp+460h+var_420]; void *
0x180001bad  xor     edx, edx; Val
0x180001baf  call    memset_0
0x180001bb4  lea     rcx, [rdi+10h]; lpCriticalSection
0x180001bb8  call    cs:__imp_EnterCriticalSection
0x180001bbf  nop     dword ptr [rax+rax+00h]
0x180001bc4  mov     rcx, rbx; pbstr
0x180001bc7  call    cs:__imp_SysStringLen
0x180001bce  nop     dword ptr [rax+rax+00h]
0x180001bd3  lea     r14, aFwauthappPutPr; "FwAuthApp::put_ProcessImageFileName"
0x180001bda  test    eax, eax
0x180001bdc  jnz     short loc_180001BEA
0x180001bde  mov     ebx, 80070057h
0x180001be3  mov     edx, ebx
0x180001be5  jmp     loc_180001DB3
0x180001bea  lea     rdx, [rsp+460h+var_440]
0x180001bef  mov     rcx, rbx
0x180001bf2  call    cs:__imp_FwGetSysPathName
0x180001bf9  nop     dword ptr [rax+rax+00h]
0x180001bfe  mov     ebx, eax
0x180001c00  test    eax, eax
0x180001c02  js      loc_180001DB1
0x180001c08  lea     rcx, [rsp+460h+var_438]
0x180001c0d  call    cs:__imp_FwGetAppBlockList
0x180001c14  nop     dword ptr [rax+rax+00h]
0x180001c19  mov     ebx, eax
0x180001c1b  test    eax, eax
0x180001c1d  js      loc_180001DB1
0x180001c23  mov     rdx, [rsp+460h+var_440]
0x180001c28  lea     rcx, [rsp+460h+var_438]
0x180001c2d  call    cs:__imp_FwImageListHasImage
0x180001c34  nop     dword ptr [rax+rax+00h]
0x180001c39  test    eax, eax
0x180001c3b  jz      short loc_180001C44
0x180001c3d  mov     ebx, 800720E7h
0x180001c42  jmp     short loc_180001BE3
0x180001c44  mov     rcx, rdi; this
0x180001c47  call    ?CreateDefaultAuthAppRules@FwAuthApp@@AEAAJXZ; FwAuthApp::CreateDefaultAuthAppRules(void)
0x180001c4c  mov     ebx, eax
0x180001c4e  test    eax, eax
0x180001c50  js      loc_180001DB1
0x180001c56  mov     rax, [rdi+48h]
0x180001c5a  lea     rcx, [rbp+360h+var_220]
0x180001c61  mov     r8d, 3
0x180001c67  mov     edx, r8d
0x180001c6a  lea     r10d, [r8+7Dh]
0x180001c6e  movups  xmm0, xmmword ptr [rax]
0x180001c71  movups  xmmword ptr [rcx], xmm0
0x180001c74  movups  xmm1, xmmword ptr [rax+10h]
0x180001c78  movups  xmmword ptr [rcx+10h], xmm1
0x180001c7c  movups  xmm0, xmmword ptr [rax+20h]
0x180001c80  movups  xmmword ptr [rcx+20h], xmm0
0x180001c84  movups  xmm1, xmmword ptr [rax+30h]
0x180001c88  movups  xmmword ptr [rcx+30h], xmm1
0x180001c8c  movups  xmm0, xmmword ptr [rax+40h]
0x180001c90  movups  xmmword ptr [rcx+40h], xmm0
0x180001c94  movups  xmm1, xmmword ptr [rax+50h]
0x180001c98  movups  xmmword ptr [rcx+50h], xmm1
0x180001c9c  movups  xmm0, xmmword ptr [rax+60h]
0x180001ca0  movups  xmmword ptr [rcx+60h], xmm0
0x180001ca4  movups  xmm1, xmmword ptr [rax+70h]
0x180001ca8  add     rax, r10
0x180001cab  movups  xmmword ptr [rcx+70h], xmm1
0x180001caf  add     rcx, r10
0x180001cb2  sub     rdx, 1
0x180001cb6  jnz     short loc_180001C6E
0x180001cb8  movups  xmm0, xmmword ptr [rax]
0x180001cbb  mov     r9, [rsp+460h+var_440]
0x180001cc0  lea     rdx, [rsp+460h+var_420]
0x180001cc5  movups  xmmword ptr [rcx], xmm0
0x180001cc8  movups  xmm1, xmmword ptr [rax+10h]
0x180001ccc  movups  xmmword ptr [rcx+10h], xmm1
0x180001cd0  movups  xmm0, xmmword ptr [rax+20h]
0x180001cd4  movups  xmmword ptr [rcx+20h], xmm0
0x180001cd8  movups  xmm1, xmmword ptr [rax+30h]
0x180001cdc  movups  xmmword ptr [rcx+30h], xmm1
0x180001ce0  movups  xmm0, xmmword ptr [rax+40h]
0x180001ce4  movups  xmmword ptr [rcx+40h], xmm0
0x180001ce8  movups  xmm1, xmmword ptr [rax+50h]
0x180001cec  movups  xmmword ptr [rcx+50h], xmm1
0x180001cf0  movups  xmm0, xmmword ptr [rax+60h]
0x180001cf4  movups  xmmword ptr [rcx+60h], xmm0
0x180001cf8  mov     rax, [rax+70h]
0x180001cfc  mov     [rcx+70h], rax
0x180001d00  mov     rax, [rdi+50h]
0x180001d04  mov     [rbp+360h+var_110], r9
0x180001d0b  movups  xmm0, xmmword ptr [rax]
0x180001d0e  movups  xmmword ptr [rdx], xmm0
0x180001d11  movups  xmm1, xmmword ptr [rax+10h]
0x180001d15  movups  xmmword ptr [rdx+10h], xmm1
0x180001d19  movups  xmm0, xmmword ptr [rax+20h]
0x180001d1d  movups  xmmword ptr [rdx+20h], xmm0
0x180001d21  movups  xmm1, xmmword ptr [rax+30h]
0x180001d25  movups  xmmword ptr [rdx+30h], xmm1
0x180001d29  movups  xmm0, xmmword ptr [rax+40h]
0x180001d2d  movups  xmmword ptr [rdx+40h], xmm0
0x180001d31  movups  xmm1, xmmword ptr [rax+50h]
0x180001d35  movups  xmmword ptr [rdx+50h], xmm1
0x180001d39  movups  xmm0, xmmword ptr [rax+60h]
0x180001d3d  movups  xmmword ptr [rdx+60h], xmm0
0x180001d41  movups  xmm1, xmmword ptr [rax+70h]
0x180001d45  add     rax, r10
0x180001d48  movups  xmmword ptr [rdx+70h], xmm1
0x180001d4c  add     rdx, r10
0x180001d4f  sub     r8, 1
0x180001d53  jnz     short loc_180001D0B
0x180001d55  movups  xmm0, xmmword ptr [rax]
0x180001d58  lea     r8, [rsp+460h+var_420]; struct _tag_FW_RULE *
0x180001d5d  mov     rcx, rdi; this
0x180001d60  movups  xmmword ptr [rdx], xmm0
0x180001d63  movups  xmm1, xmmword ptr [rax+10h]
0x180001d67  movups  xmmword ptr [rdx+10h], xmm1
0x180001d6b  movups  xmm0, xmmword ptr [rax+20h]
0x180001d6f  movups  xmmword ptr [rdx+20h], xmm0
0x180001d73  movups  xmm1, xmmword ptr [rax+30h]
0x180001d77  movups  xmmword ptr [rdx+30h], xmm1
0x180001d7b  movups  xmm0, xmmword ptr [rax+40h]
0x180001d7f  movups  xmmword ptr [rdx+40h], xmm0
0x180001d83  movups  xmm1, xmmword ptr [rax+50h]
0x180001d87  movups  xmmword ptr [rdx+50h], xmm1
0x180001d8b  movups  xmm0, xmmword ptr [rax+60h]
0x180001d8f  movups  xmmword ptr [rdx+60h], xmm0
0x180001d93  mov     rax, [rax+70h]
0x180001d97  mov     [rdx+70h], rax
0x180001d9b  lea     rdx, [rbp+360h+var_220]; struct _tag_FW_RULE *
0x180001da2  mov     [rbp+360h+var_310], r9
0x180001da6  call    ?SetRules@FwAuthApp@@AEAAJPEBU_tag_FW_RULE@@0@Z; FwAuthApp::SetRules(_tag_FW_RULE const *,_tag_FW_RULE const *)
0x180001dab  mov     ebx, eax
0x180001dad  test    eax, eax
0x180001daf  jns     short loc_180001DC2
0x180001db1  mov     edx, eax
0x180001db3  mov     rcx, r14
0x180001db6  call    cs:__imp_FwReportReturnError
0x180001dbd  nop     dword ptr [rax+rax+00h]
0x180001dc2  lea     rcx, [rdi+10h]; lpCriticalSection
0x180001dc6  call    cs:__imp_LeaveCriticalSection
0x180001dcd  nop     dword ptr [rax+rax+00h]
0x180001dd2  lea     rcx, [rsp+460h+var_438]
0x180001dd7  call    cs:__imp_FwImageListDestroy
0x180001dde  nop     dword ptr [rax+rax+00h]
0x180001de3  mov     rcx, [rsp+460h+var_440]
0x180001de8  call    cs:__imp_FwBaseFree
0x180001def  nop     dword ptr [rax+rax+00h]
0x180001df4  test    ebx, ebx
0x180001df6  jns     short loc_180001E0B
0x180001df8  mov     edx, ebx
0x180001dfa  mov     rcx, r14
0x180001dfd  call    cs:__imp_FwReportReturnError
0x180001e04  nop     dword ptr [rax+rax+00h]
0x180001e09  mov     ebx, eax
0x180001e0b  mov     eax, ebx
0x180001e0d  mov     rcx, [rbp+360h+var_20]
0x180001e14  xor     rcx, rsp; StackCookie
0x180001e17  call    __security_check_cookie
0x180001e1c  lea     r11, [rsp+460h+var_10]
0x180001e24  mov     rbx, [r11+30h]
0x180001e28  mov     rsi, [r11+38h]
0x180001e2c  mov     rsp, r11
0x180001e2f  pop     r14
0x180001e31  pop     rdi
0x180001e32  pop     rbp
0x180001e33  retn
```
