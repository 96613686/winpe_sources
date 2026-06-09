# OapPathNameToFormatName

- ea: `0x1800230fc`
- end: `0x18002320c`
- name: `OapPathNameToFormatName`
- size: `272`
- prototype: `__int64 __fastcall(LPCWSTR lpwcsPathName)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180022be0`

## callees

- `0x18000173c`
- `0x18000178c`
- `0x180003bb4`
- `0x1800230fc`
- `0x1800273b0`

## import_xrefs

- `mqrt!MQPathNameToFormatName` at `0x180023138`
- `mqrt!MQPathNameToFormatName` at `0x1800231af`
- `mqrt!MQPathNameToFormatName` at `0x180023138`
- `mqrt!MQPathNameToFormatName` at `0x1800231af`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HRESULT __fastcall OapPathNameToFormatName(LPCWSTR lpwcsPathName, _QWORD *a2)
{
  HRESULT result; // eax
  WCHAR *v5; // rax
  WCHAR *v6; // rbx
  HRESULT v7; // esi
  DWORD dwFormatNameLength; // [rsp+20h] [rbp-128h] BYREF
  WCHAR *v9; // [rsp+28h] [rbp-120h]
  WCHAR wcsFormatName[128]; // [rsp+30h] [rbp-118h] BYREF

  dwFormatNameLength = 128;
  result = MQPathNameToFormatName(lpwcsPathName, wcsFormatName, &dwFormatNameLength);
  if ( result >= 0 )
  {
    ATL::CComBSTR::operator=(a2, wcsFormatName);
    return *a2 == 0 ? 0x8007000E : 0;
  }
  if ( result == -1072824289 )
  {
    v5 = (WCHAR *)operator new(saturated_mul(dwFormatNameLength, 2u));
    v6 = v5;
    v9 = v5;
    if ( !v5 )
    {
      operator delete(0);
      return -2147024882;
    }
    v7 = MQPathNameToFormatName(lpwcsPathName, v5, &dwFormatNameLength);
    if ( v7 < 0 )
      goto LABEL_9;
    ATL::CComBSTR::operator=(a2, v6);
    if ( !*a2 )
    {
      v7 = -2147024882;
LABEL_9:
      operator delete(v6);
      return v7;
    }
    operator delete(v6);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800230fc  mov     [rsp+arg_10], rbx
0x180023101  mov     [rsp+arg_18], rsi
0x180023106  push    rdi
0x180023107  sub     rsp, 140h
0x18002310e  mov     rax, cs:__security_cookie
0x180023115  xor     rax, rsp
0x180023118  mov     [rsp+148h+var_18], rax
0x180023120  mov     rdi, rdx
0x180023123  mov     rsi, rcx
0x180023126  mov     [rsp+148h+dwFormatNameLength], 80h
0x18002312e  lea     r8, [rsp+148h+dwFormatNameLength]; lpdwFormatNameLength
0x180023133  lea     rdx, [rsp+148h+wcsFormatName]; lpwcsFormatName
0x180023138  call    cs:__imp_MQPathNameToFormatName
0x18002313e  test    eax, eax
0x180023140  js      short loc_180023163
0x180023142  lea     rdx, [rsp+148h+wcsFormatName]
0x180023147  mov     rcx, rdi
0x18002314a  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEB_W@Z; ATL::CComBSTR::operator=(wchar_t const *)
0x18002314f  mov     rax, [rdi]
0x180023152  neg     rax
0x180023155  sbb     eax, eax
0x180023157  not     eax
0x180023159  and     eax, 8007000Eh
0x18002315e  jmp     loc_1800231E7
0x180023163  cmp     eax, 0C00E001Fh
0x180023168  jnz     short loc_1800231E7
0x18002316a  mov     ecx, [rsp+148h+dwFormatNameLength]
0x18002316e  mov     eax, 2
0x180023173  mul     rcx
0x180023176  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18002317d  cmovb   rax, rcx
0x180023181  mov     rcx, rax; Size
0x180023184  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180023189  mov     rbx, rax
0x18002318c  mov     [rsp+148h+var_120], rax
0x180023191  test    rax, rax
0x180023194  jnz     short loc_1800231A4
0x180023196  xor     ecx, ecx; Block
0x180023198  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002319d  mov     eax, 8007000Eh
0x1800231a2  jmp     short loc_1800231E7
0x1800231a4  lea     r8, [rsp+148h+dwFormatNameLength]; lpdwFormatNameLength
0x1800231a9  mov     rdx, rbx; lpwcsFormatName
0x1800231ac  mov     rcx, rsi; lpwcsPathName
0x1800231af  call    cs:__imp_MQPathNameToFormatName
0x1800231b5  mov     esi, eax
0x1800231b7  test    eax, eax
0x1800231b9  js      short loc_1800231D1
0x1800231bb  mov     rdx, rbx
0x1800231be  mov     rcx, rdi
0x1800231c1  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEB_W@Z; ATL::CComBSTR::operator=(wchar_t const *)
0x1800231c6  cmp     qword ptr [rdi], 0
0x1800231ca  jnz     short loc_1800231DD
0x1800231cc  mov     esi, 8007000Eh
0x1800231d1  mov     rcx, rbx; Block
0x1800231d4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800231d9  mov     eax, esi
0x1800231db  jmp     short loc_1800231E7
0x1800231dd  mov     rcx, rbx; Block
0x1800231e0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800231e5  xor     eax, eax
0x1800231e7  mov     rcx, [rsp+148h+var_18]
0x1800231ef  xor     rcx, rsp; StackCookie
0x1800231f2  call    __security_check_cookie
0x1800231f7  lea     r11, [rsp+148h+var_8]
0x1800231ff  mov     rbx, [r11+20h]
0x180023203  mov     rsi, [r11+28h]
0x180023207  mov     rsp, r11
0x18002320a  pop     rdi
0x18002320b  retn
```
