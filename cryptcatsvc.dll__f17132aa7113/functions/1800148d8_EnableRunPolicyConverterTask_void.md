# EnableRunPolicyConverterTask(void)

- ea: `0x1800148d8`
- end: `0x180014afd`
- name: `?EnableRunPolicyConverterTask@@YAKXZ`
- size: `549`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180009b30`

## callees

- `0x18000be40`
- `0x1800148d8`
- `0x180022010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180014963`
- `OLEAUT32!__imp_VariantInit` at `0x180014963`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001494f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001494f`

## pseudocode

```c
__int64 EnableRunPolicyConverterTask(void)
{
  HRESULT v0; // ebx
  __int64 v1; // rax
  __int64 (__fastcall *v2)(LPVOID, VARIANTARG *, VARIANTARG *, VARIANTARG *, __int128 *); // rax
  __int64 v3; // rax
  VARIANTARG v5; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v6; // [rsp+60h] [rbp-A0h] BYREF
  IRecordInfo *pRecInfo; // [rsp+70h] [rbp-90h]
  VARIANTARG v8; // [rsp+80h] [rbp-80h] BYREF
  VARIANTARG v9; // [rsp+A0h] [rbp-60h] BYREF
  __int64 *v10; // [rsp+C0h] [rbp-40h] BYREF
  LPVOID ppv; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v12; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v13; // [rsp+D8h] [rbp-28h]
  IID rclsid; // [rsp+E0h] [rbp-20h] BYREF
  VARIANTARG pvarg; // [rsp+F0h] [rbp-10h] BYREF

  ppv = 0;
  v12 = 0;
  v10 = 0;
  v13 = 0;
  rclsid.Data1 = 260519583;
  *(_DWORD *)&rclsid.Data2 = 1291625701;
  memset(&pvarg, 0, sizeof(pvarg));
  *(_DWORD *)rclsid.Data4 = -428654915;
  *(_DWORD *)&rclsid.Data4[4] = -579713771;
  v0 = CoCreateInstance(&rclsid, 0, 1u, &GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85, &ppv);
  if ( v0 >= 0 )
  {
    VariantInit(&pvarg);
    v6 = *(_OWORD *)&pvarg.vt;
    v1 = *(_QWORD *)ppv;
    pRecInfo = pvarg.pRecInfo;
    v8 = pvarg;
    v2 = *(__int64 (__fastcall **)(LPVOID, VARIANTARG *, VARIANTARG *, VARIANTARG *, __int128 *))(v1 + 80);
    v9 = pvarg;
    v5 = pvarg;
    v0 = v2(ppv, &v5, &v9, &v8, &v6);
    if ( v0 >= 0 )
    {
      v0 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, __int64 *))(*(_QWORD *)ppv + 56LL))(
             ppv,
             L"\\Microsoft\\Windows\\AppID",
             &v12);
      if ( v0 >= 0 )
      {
        v0 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 **))(*(_QWORD *)v12 + 104LL))(
               v12,
               L"PolicyConverter",
               &v10);
        if ( v0 >= 0 )
        {
          v0 = (*(__int64 (__fastcall **)(__int64 *, __int64))(*v10 + 88))(v10, 0xFFFFFFFFLL);
          if ( v0 >= 0 )
          {
            v3 = *v10;
            v5 = pvarg;
            v0 = (*(__int64 (__fastcall **)(__int64 *, VARIANTARG *, __int64))(v3 + 104))(v10, &v5, 2);
          }
        }
      }
    }
  }
  if ( v13 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  if ( v10 )
    (*(void (__fastcall **)(__int64 *))(*v10 + 16))(v10);
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( v0 < 0 )
  {
    if ( (v0 & 0x1FFF0000) == 0x70000 )
      return (unsigned __int16)v0;
  }
  else
  {
    return 0;
  }
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x1800148d8  mov     [rsp-8+arg_0], rbx
0x1800148dd  push    rbp
0x1800148de  lea     rbp, [rsp-10h]
0x1800148e3  sub     rsp, 110h
0x1800148ea  mov     rax, cs:__security_cookie
0x1800148f1  xor     rax, rsp
0x1800148f4  mov     [rbp+10h+var_8], rax
0x1800148f8  xor     eax, eax
0x1800148fa  mov     [rbp+10h+var_48], 0
0x180014902  xor     edx, edx; pUnkOuter
0x180014904  mov     qword ptr [rbp+10h+pvarg+10h], rax
0x180014908  mov     [rbp+10h+var_40], rax
0x18001490c  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x180014913  mov     [rbp+10h+var_50], rax
0x180014917  lea     rcx, [rbp+10h+rclsid]; rclsid
0x18001491b  mov     [rbp+10h+var_38], rax
0x18001491f  xorps   xmm0, xmm0
0x180014922  lea     rax, [rbp+10h+var_48]
0x180014926  mov     [rbp+10h+rclsid.Data1], 0F87369Fh
0x18001492d  lea     r8d, [rdx+1]; dwClsContext
0x180014931  mov     dword ptr [rbp+10h+rclsid.Data2], 4CFCA4E5h
0x180014938  movups  xmmword ptr [rbp+10h+pvarg], xmm0
0x18001493c  mov     dword ptr [rbp+10h+rclsid.Data4], 0E6733EBDh
0x180014943  mov     dword ptr [rbp+10h+rclsid.Data4+4], 0DD724515h
0x18001494a  mov     [rsp+110h+ppv], rax; ppv
0x18001494f  call    cs:__imp_CoCreateInstance
0x180014955  mov     ebx, eax
0x180014957  test    eax, eax
0x180014959  js      loc_180014A71
0x18001495f  lea     rcx, [rbp+10h+pvarg]; pvarg
0x180014963  call    cs:__imp_VariantInit
0x180014969  movups  xmm1, xmmword ptr [rbp+10h+pvarg]
0x18001496d  lea     rdx, [rsp+110h+var_B0]
0x180014972  mov     rcx, [rbp+10h+var_48]
0x180014976  movsd   xmm0, qword ptr [rbp+10h+pvarg+10h]
0x18001497b  lea     r9, [rbp+10h+var_90]
0x18001497f  mov     [rsp+110h+ppv], rdx
0x180014984  lea     r8, [rbp+10h+var_70]
0x180014988  lea     rdx, [rsp+110h+var_D0]
0x18001498d  movaps  [rsp+110h+var_B0], xmm1
0x180014992  mov     rax, [rcx]
0x180014995  movsd   [rsp+110h+var_A0], xmm0
0x18001499b  movaps  [rbp+10h+var_90], xmm1
0x18001499f  movsd   [rbp+10h+var_80], xmm0
0x1800149a4  mov     rax, [rax+50h]
0x1800149a8  movaps  [rbp+10h+var_70], xmm1
0x1800149ac  movsd   [rbp+10h+var_60], xmm0
0x1800149b1  movaps  [rsp+110h+var_D0], xmm1
0x1800149b6  movsd   [rsp+110h+var_C0], xmm0
0x1800149bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800149c1  mov     ebx, eax
0x1800149c3  test    eax, eax
0x1800149c5  js      loc_180014A71
0x1800149cb  mov     rcx, [rbp+10h+var_48]
0x1800149cf  lea     r8, [rbp+10h+var_40]
0x1800149d3  lea     rdx, aMicrosoftWindo; "\\Microsoft\\Windows\\AppID"
0x1800149da  mov     rax, [rcx]
0x1800149dd  mov     rax, [rax+38h]
0x1800149e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800149e6  mov     ebx, eax
0x1800149e8  test    eax, eax
0x1800149ea  js      loc_180014A71
0x1800149f0  mov     rcx, [rbp+10h+var_40]
0x1800149f4  lea     r8, [rbp+10h+var_50]
0x1800149f8  lea     rdx, aPolicyconverte; "PolicyConverter"
0x1800149ff  mov     rax, [rcx]
0x180014a02  mov     rax, [rax+68h]
0x180014a06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a0b  mov     ebx, eax
0x180014a0d  test    eax, eax
0x180014a0f  js      short loc_180014A71
0x180014a11  mov     rcx, [rbp+10h+var_50]
0x180014a15  or      edx, 0FFFFFFFFh
0x180014a18  mov     rax, [rcx]
0x180014a1b  mov     rax, [rax+58h]
0x180014a1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a24  mov     ebx, eax
0x180014a26  test    eax, eax
0x180014a28  js      short loc_180014A71
0x180014a2a  mov     rcx, [rbp+10h+var_50]
0x180014a2e  lea     rdx, [rbp+10h+var_38]
0x180014a32  movups  xmm0, xmmword ptr [rbp+10h+pvarg]
0x180014a36  xor     r9d, r9d
0x180014a39  mov     [rsp+110h+var_E8], rdx
0x180014a3e  movsd   xmm1, qword ptr [rbp+10h+pvarg+10h]
0x180014a43  lea     rdx, LocaleName
0x180014a4a  mov     rax, [rcx]
0x180014a4d  mov     [rsp+110h+ppv], rdx
0x180014a52  lea     rdx, [rsp+110h+var_D0]
0x180014a57  lea     r8d, [r9+2]
0x180014a5b  movaps  [rsp+110h+var_D0], xmm0
0x180014a60  movsd   [rsp+110h+var_C0], xmm1
0x180014a66  mov     rax, [rax+68h]
0x180014a6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a6f  mov     ebx, eax
0x180014a71  mov     rcx, [rbp+10h+var_38]
0x180014a75  test    rcx, rcx
0x180014a78  jz      short loc_180014A86
0x180014a7a  mov     rax, [rcx]
0x180014a7d  mov     rax, [rax+10h]
0x180014a81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a86  mov     rcx, [rbp+10h+var_50]
0x180014a8a  test    rcx, rcx
0x180014a8d  jz      short loc_180014A9B
0x180014a8f  mov     rax, [rcx]
0x180014a92  mov     rax, [rax+10h]
0x180014a96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a9b  mov     rcx, [rbp+10h+var_40]
0x180014a9f  test    rcx, rcx
0x180014aa2  jz      short loc_180014AB0
0x180014aa4  mov     rax, [rcx]
0x180014aa7  mov     rax, [rax+10h]
0x180014aab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014ab0  mov     rcx, [rbp+10h+var_48]
0x180014ab4  test    rcx, rcx
0x180014ab7  jz      short loc_180014AC5
0x180014ab9  mov     rax, [rcx]
0x180014abc  mov     rax, [rax+10h]
0x180014ac0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014ac5  test    ebx, ebx
0x180014ac7  js      short loc_180014ACD
0x180014ac9  xor     ebx, ebx
0x180014acb  jmp     short loc_180014ADE
0x180014acd  mov     eax, ebx
0x180014acf  and     eax, 1FFF0000h
0x180014ad4  cmp     eax, 70000h
0x180014ad9  jnz     short loc_180014ADE
0x180014adb  movzx   ebx, bx
0x180014ade  mov     eax, ebx
0x180014ae0  mov     rcx, [rbp+10h+var_8]
0x180014ae4  xor     rcx, rsp; StackCookie
0x180014ae7  call    __security_check_cookie
0x180014aec  mov     rbx, [rsp+110h+arg_0]
0x180014af4  add     rsp, 110h
0x180014afb  pop     rbp
0x180014afc  retn
```
