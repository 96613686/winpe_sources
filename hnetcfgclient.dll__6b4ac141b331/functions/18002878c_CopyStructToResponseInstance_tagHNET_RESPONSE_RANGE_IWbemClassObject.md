# CopyStructToResponseInstance(tagHNET_RESPONSE_RANGE *,IWbemClassObject *)

- ea: `0x18002878c`
- end: `0x180028865`
- name: `?CopyStructToResponseInstance@@YAJPEAUtagHNET_RESPONSE_RANGE@@PEAUIWbemClassObject@@@Z`
- size: `217`
- prototype: `__int64 __fastcall(BYTE *, struct IWbemClassObject *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800283f8`

## callees

- `0x18002878c`
- `0x18002f010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1800287b0`
- `OLEAUT32!__imp_VariantInit` at `0x1800287b0`

## string_xrefs

- `0x1800287cf`: `IPProtocol`

## pseudocode

```c
__int64 __fastcall CopyStructToResponseInstance(BYTE *a1, struct IWbemClassObject *a2)
{
  __int64 result; // rax
  VARIANTARG pvarg; // [rsp+30h] [rbp-28h] BYREF

  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  pvarg.vt = 17;
  pvarg.bVal = *a1;
  result = ((__int64 (__fastcall *)(struct IWbemClassObject *, const unsigned __int16 *, _QWORD, VARIANTARG *, _DWORD))a2->lpVtbl->Put)(
             a2,
             L"IPProtocol",
             0,
             &pvarg,
             0);
  if ( !(_DWORD)result )
  {
    pvarg.vt = 3;
    pvarg.lVal = *((unsigned __int16 *)a1 + 1);
    result = ((__int64 (__fastcall *)(struct IWbemClassObject *, const unsigned __int16 *, _QWORD, VARIANTARG *, _DWORD))a2->lpVtbl->Put)(
               a2,
               L"StartPort",
               0,
               &pvarg,
               0);
    if ( !(_DWORD)result )
    {
      pvarg.lVal = *((unsigned __int16 *)a1 + 2);
      return ((__int64 (__fastcall *)(struct IWbemClassObject *, const unsigned __int16 *, _QWORD, VARIANTARG *, _DWORD))a2->lpVtbl->Put)(
               a2,
               L"EndPort",
               0,
               &pvarg,
               0);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18002878c  mov     [rsp+arg_0], rbx
0x180028791  push    rdi
0x180028792  sub     rsp, 50h
0x180028796  mov     rdi, rcx
0x180028799  xorps   xmm0, xmm0
0x18002879c  xor     eax, eax
0x18002879e  lea     rcx, [rsp+58h+pvarg]; pvarg
0x1800287a3  movups  xmmword ptr [rsp+58h+pvarg], xmm0
0x1800287a8  mov     qword ptr [rsp+58h+pvarg+10h], rax
0x1800287ad  mov     rbx, rdx
0x1800287b0  call    cs:__imp_VariantInit
0x1800287b6  mov     eax, 11h
0x1800287bb  mov     [rsp+58h+var_38], 0
0x1800287c3  mov     word ptr [rsp+58h+pvarg], ax
0x1800287c8  lea     r9, [rsp+58h+pvarg]
0x1800287cd  mov     al, [rdi]
0x1800287cf  lea     rdx, ?c_wszIPProtocol@@3QBGB; "IPProtocol"
0x1800287d6  mov     byte ptr [rsp+58h+pvarg+8], al
0x1800287da  xor     r8d, r8d
0x1800287dd  mov     rax, [rbx]
0x1800287e0  mov     rcx, rbx
0x1800287e3  mov     rax, [rax+28h]
0x1800287e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800287ec  test    eax, eax
0x1800287ee  jnz     short loc_18002885A
0x1800287f0  mov     eax, 3
0x1800287f5  mov     [rsp+58h+var_38], 0
0x1800287fd  mov     word ptr [rsp+58h+pvarg], ax
0x180028802  lea     r9, [rsp+58h+pvarg]
0x180028807  movzx   eax, word ptr [rdi+2]
0x18002880b  lea     rdx, ?c_wszStartPort@@3QBGB; "StartPort"
0x180028812  mov     dword ptr [rsp+58h+pvarg+8], eax
0x180028816  xor     r8d, r8d
0x180028819  mov     rax, [rbx]
0x18002881c  mov     rcx, rbx
0x18002881f  mov     rax, [rax+28h]
0x180028823  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028828  test    eax, eax
0x18002882a  jnz     short loc_18002885A
0x18002882c  movzx   eax, word ptr [rdi+4]
0x180028830  lea     r9, [rsp+58h+pvarg]
0x180028835  mov     dword ptr [rsp+58h+pvarg+8], eax
0x180028839  lea     rdx, ?c_wszEndPort@@3QBGB; "EndPort"
0x180028840  mov     rax, [rbx]
0x180028843  xor     r8d, r8d
0x180028846  mov     rcx, rbx
0x180028849  mov     [rsp+58h+var_38], 0
0x180028851  mov     rax, [rax+28h]
0x180028855  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002885a  mov     rbx, [rsp+58h+arg_0]
0x18002885f  add     rsp, 50h
0x180028863  pop     rdi
0x180028864  retn
```
