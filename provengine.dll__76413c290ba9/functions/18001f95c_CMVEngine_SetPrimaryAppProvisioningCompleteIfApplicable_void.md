# CMVEngine::SetPrimaryAppProvisioningCompleteIfApplicable(void)

- ea: `0x18001f95c`
- end: `0x18001fa5e`
- name: `?SetPrimaryAppProvisioningCompleteIfApplicable@CMVEngine@@AEAAJXZ`
- size: `258`
- prototype: `__int64 __fastcall(CMVEngine *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180018068`

## callees

- `0x1800010c8`
- `0x1800098dc`
- `0x18001f95c`
- `0x180033b88`
- `0x180043750`
- `0x180047010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18001f97f`
- `OLEAUT32!__imp_VariantInit` at `0x18001f97f`
- `OLEAUT32!__imp_VariantClear` at `0x18001fa3d`
- `OLEAUT32!__imp_VariantClear` at `0x18001fa3d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMVEngine::SetPrimaryAppProvisioningCompleteIfApplicable(CMVEngine *this)
{
  int v2; // eax
  int v3; // ebx
  __int64 v4; // rdx
  int v5; // eax
  int v7; // [rsp+20h] [rbp-78h]
  int v8; // [rsp+30h] [rbp-68h] BYREF
  VARIANTARG pvarg; // [rsp+38h] [rbp-60h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v10; // [rsp+50h] [rbp-48h] BYREF
  int *v11; // [rsp+70h] [rbp-28h]
  __int64 v12; // [rsp+78h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  VariantInit(&pvarg);
  v2 = (*(__int64 (__fastcall **)(CMVEngine *, const unsigned __int16 *, VARIANTARG *))(*(_QWORD *)this + 56LL))(
         this,
         L"slotstatus",
         &pvarg);
  v3 = v2;
  if ( v2 == -2147024894 )
    goto LABEL_10;
  if ( v2 >= 0 )
  {
    if ( pvarg.lVal == 1 )
    {
      v5 = MvSetPrimaryAppProvisioningComplete();
      v3 = v5;
      if ( (unsigned int)dword_18005A000 > 5 )
      {
        v8 = v5;
        v11 = &v8;
        v12 = 4;
        tlgWriteTransfer_EventWriteTransfer(
          (__int64)&dword_18005A000,
          (unsigned __int8 *)byte_18004F363,
          0,
          0,
          3u,
          &v10);
      }
      if ( v3 < 0 )
      {
        v4 = 3250;
        goto LABEL_9;
      }
    }
LABEL_10:
    v3 = 0;
    goto LABEL_11;
  }
  v4 = 3238;
LABEL_9:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v4,
    (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\provisionengine.cpp",
    (const char *)(unsigned int)v3,
    v7);
LABEL_11:
  VariantClear(&pvarg);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18001f95c  push    rbx
0x18001f95e  sub     rsp, 90h
0x18001f965  mov     rax, cs:__security_cookie
0x18001f96c  xor     rax, rsp
0x18001f96f  mov     [rsp+98h+var_18], rax
0x18001f977  mov     rbx, rcx
0x18001f97a  lea     rcx, [rsp+98h+pvarg]; pvarg
0x18001f97f  call    cs:__imp_VariantInit
0x18001f985  nop
0x18001f986  mov     rax, [rbx]
0x18001f989  lea     r8, [rsp+98h+pvarg]
0x18001f98e  lea     rdx, ?gc_wszSlotStatusContext@@3QBGB; "slotstatus"
0x18001f995  mov     rcx, rbx
0x18001f998  mov     rax, [rax+38h]
0x18001f99c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f9a1  mov     ebx, eax
0x18001f9a3  cmp     eax, 80070002h
0x18001f9a8  jz      loc_18001FA36
0x18001f9ae  test    eax, eax
0x18001f9b0  jns     short loc_18001F9B9
0x18001f9b2  mov     edx, 0CA6h
0x18001f9b7  jmp     short loc_18001FA1D
0x18001f9b9  cmp     dword ptr [rsp+98h+pvarg+8], 1
0x18001f9be  jnz     short loc_18001FA36
0x18001f9c0  call    ?MvSetPrimaryAppProvisioningComplete@@YAJH@Z; MvSetPrimaryAppProvisioningComplete(int)
0x18001f9c5  mov     ebx, eax
0x18001f9c7  mov     ecx, cs:dword_18005A000
0x18001f9cd  cmp     ecx, 5
0x18001f9d0  jbe     short loc_18001FA14
0x18001f9d2  mov     [rsp+98h+var_68], eax
0x18001f9d6  lea     rax, [rsp+98h+var_68]
0x18001f9db  mov     [rsp+98h+var_28], rax
0x18001f9e0  mov     [rsp+98h+var_20], 4
0x18001f9e9  lea     rax, [rsp+98h+var_48]
0x18001f9ee  mov     [rsp+98h+var_70], rax
0x18001f9f3  mov     [rsp+98h+var_78], 3; int
0x18001f9fb  xor     r9d, r9d
0x18001f9fe  xor     r8d, r8d
0x18001fa01  lea     rdx, byte_18004F363
0x18001fa08  lea     rcx, dword_18005A000
0x18001fa0f  call    _tlgWriteTransfer_EventWriteTransfer
0x18001fa14  test    ebx, ebx
0x18001fa16  jns     short loc_18001FA36
0x18001fa18  mov     edx, 0CB2h; void *
0x18001fa1d  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18001fa24  mov     r9d, ebx; char *
0x18001fa27  mov     rcx, [rsp+98h]; this
0x18001fa2f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fa34  jmp     short loc_18001FA38
0x18001fa36  xor     ebx, ebx
0x18001fa38  lea     rcx, [rsp+98h+pvarg]; pvarg
0x18001fa3d  call    cs:__imp_VariantClear
0x18001fa43  mov     eax, ebx
0x18001fa45  mov     rcx, [rsp+98h+var_18]
0x18001fa4d  xor     rcx, rsp; StackCookie
0x18001fa50  call    __security_check_cookie
0x18001fa55  add     rsp, 90h
0x18001fa5c  pop     rbx
0x18001fa5d  retn
```
