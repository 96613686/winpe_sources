# CMVEngine::UpdateSessionStateForContext(ProvisioningResult)

- ea: `0x180020450`
- end: `0x180020567`
- name: `?UpdateSessionStateForContext@CMVEngine@@AEAAXW4ProvisioningResult@@@Z`
- size: `279`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x18001240c`
- `0x18001d924`

## callees

- `0x180020450`
- `0x180047010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180020467`
- `OLEAUT32!__imp_VariantInit` at `0x1800204ba`
- `OLEAUT32!__imp_VariantInit` at `0x1800204fc`
- `OLEAUT32!__imp_VariantInit` at `0x180020467`
- `OLEAUT32!__imp_VariantInit` at `0x1800204ba`
- `OLEAUT32!__imp_VariantInit` at `0x1800204fc`
- `OLEAUT32!__imp_VariantClear` at `0x1800204b0`
- `OLEAUT32!__imp_VariantClear` at `0x1800204f2`
- `OLEAUT32!__imp_VariantClear` at `0x180020556`
- `OLEAUT32!__imp_VariantClear` at `0x1800204b0`
- `OLEAUT32!__imp_VariantClear` at `0x1800204f2`
- `OLEAUT32!__imp_VariantClear` at `0x180020556`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HRESULT __fastcall CMVEngine::UpdateSessionStateForContext(__int64 a1, int a2)
{
  __int64 Lo; // rdi
  int v5; // eax
  VARIANTARG pvarg; // [rsp+20h] [rbp-20h] BYREF

  VariantInit(&pvarg);
  if ( (*(int (__fastcall **)(__int64, const unsigned __int16 *, VARIANTARG *))(*(_QWORD *)a1 + 56LL))(
         a1,
         L"PrimaryModem",
         &pvarg) >= 0
    && pvarg.vt == 11
    && pvarg.iVal == -1 )
  {
    VariantClear(&pvarg);
    VariantInit(&pvarg);
    if ( (*(int (__fastcall **)(__int64, const unsigned __int16 *, VARIANTARG *))(*(_QWORD *)a1 + 56LL))(
           a1,
           L"slot",
           &pvarg) >= 0
      && pvarg.vt == 19 )
    {
      Lo = pvarg.cyVal.Lo;
      VariantClear(&pvarg);
      VariantInit(&pvarg);
      if ( (*(int (__fastcall **)(__int64, const unsigned __int16 *, VARIANTARG *))(*(_QWORD *)a1 + 56LL))(
             a1,
             L"slotstatus",
             &pvarg) >= 0
        && pvarg.vt == 19 )
      {
        if ( pvarg.lVal )
        {
          if ( a2 )
            v5 = 3;
          else
            v5 = 2;
        }
        else
        {
          v5 = 1;
        }
        if ( *(_DWORD *)(a1 + 4 * Lo + 16) > v5 )
          v5 = *(_DWORD *)(a1 + 4 * Lo + 16);
        *(_DWORD *)(a1 + 4 * Lo + 16) = v5;
      }
    }
  }
  return VariantClear(&pvarg);
}

```

## disassembly

```asm
0x180020450  push    rbp
0x180020452  push    rbx
0x180020453  push    rsi
0x180020454  push    rdi
0x180020455  push    r14
0x180020457  mov     rbp, rsp
0x18002045a  sub     rsp, 40h
0x18002045e  mov     esi, edx
0x180020460  mov     rbx, rcx
0x180020463  lea     rcx, [rbp+pvarg]; pvarg
0x180020467  call    cs:__imp_VariantInit
0x18002046d  nop
0x18002046e  mov     rax, [rbx]
0x180020471  lea     r8, [rbp+pvarg]
0x180020475  lea     rdx, ?gc_wszPrimaryModem@@3QBGB; "PrimaryModem"
0x18002047c  mov     rcx, rbx
0x18002047f  mov     rax, [rax+38h]
0x180020483  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020488  test    eax, eax
0x18002048a  js      loc_180020552
0x180020490  mov     eax, 0Bh
0x180020495  cmp     ax, word ptr [rbp+pvarg]
0x180020499  jnz     loc_180020552
0x18002049f  or      eax, 0FFFFFFFFh
0x1800204a2  cmp     ax, word ptr [rbp+pvarg+8]
0x1800204a6  jnz     loc_180020552
0x1800204ac  lea     rcx, [rbp+pvarg]; pvarg
0x1800204b0  call    cs:__imp_VariantClear
0x1800204b6  lea     rcx, [rbp+pvarg]; pvarg
0x1800204ba  call    cs:__imp_VariantInit
0x1800204c0  mov     rax, [rbx]
0x1800204c3  lea     r8, [rbp+pvarg]
0x1800204c7  lea     rdx, ?gc_wszSlotContext@@3QBGB; "slot"
0x1800204ce  mov     rcx, rbx
0x1800204d1  mov     rax, [rax+38h]
0x1800204d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800204da  test    eax, eax
0x1800204dc  js      short loc_180020552
0x1800204de  mov     r14d, 13h
0x1800204e4  cmp     r14w, word ptr [rbp+pvarg]
0x1800204e9  jnz     short loc_180020552
0x1800204eb  mov     edi, dword ptr [rbp+pvarg+8]
0x1800204ee  lea     rcx, [rbp+pvarg]; pvarg
0x1800204f2  call    cs:__imp_VariantClear
0x1800204f8  lea     rcx, [rbp+pvarg]; pvarg
0x1800204fc  call    cs:__imp_VariantInit
0x180020502  mov     rax, [rbx]
0x180020505  lea     r8, [rbp+pvarg]
0x180020509  lea     rdx, ?gc_wszSlotStatusContext@@3QBGB; "slotstatus"
0x180020510  mov     rcx, rbx
0x180020513  mov     rax, [rax+38h]
0x180020517  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002051c  test    eax, eax
0x18002051e  js      short loc_180020552
0x180020520  cmp     r14w, word ptr [rbp+pvarg]
0x180020525  jnz     short loc_180020552
0x180020527  mov     ecx, [rbx+rdi*4+10h]
0x18002052b  cmp     dword ptr [rbp+pvarg+8], 0
0x18002052f  jz      short loc_180020542
0x180020531  test    esi, esi
0x180020533  jz      short loc_18002053B
0x180020535  lea     eax, [r14-10h]
0x180020539  jmp     short loc_180020547
0x18002053b  mov     eax, 2
0x180020540  jmp     short loc_180020547
0x180020542  mov     eax, 1
0x180020547  cmp     ecx, eax
0x180020549  cmovg   eax, ecx
0x18002054c  mov     [rbx+rdi*4+10h], eax
0x180020550  jmp     short $+2
0x180020552  lea     rcx, [rbp+pvarg]; pvarg
0x180020556  call    cs:__imp_VariantClear
0x18002055c  add     rsp, 40h
0x180020560  pop     r14
0x180020562  pop     rdi
0x180020563  pop     rsi
0x180020564  pop     rbx
0x180020565  pop     rbp
0x180020566  retn
```
