# PerflibciBuildCounterSet

- ea: `0x18000cc70`
- end: `0x18000d151`
- name: `PerflibciBuildCounterSet`
- size: `1249`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config`

## callers

- `0x18000d158`

## callees

- `0x180002dd0`
- `0x180005da0`
- `0x180007740`
- `0x180008050`
- `0x18000cc70`
- `0x18000d478`
- `0x18000d750`
- `0x18000d9c4`
- `0x18000da58`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000cff2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000d069`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000d094`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000cff2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000d069`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000d094`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d121`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d121`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d0cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d0cf`

## pseudocode

```c
__int64 __fastcall PerflibciBuildCounterSet(__int64 a1, __int64 a2, _DWORD *a3, __int64 a4)
{
  DWORD Value; // edi
  HKEY hKey; // [rsp+48h] [rbp-21h] BYREF
  BYTE v10[4]; // [rsp+50h] [rbp-19h]
  BYTE v11[4]; // [rsp+54h] [rbp-15h]
  BYTE Data[4]; // [rsp+58h] [rbp-11h]
  _DWORD v13[2]; // [rsp+5Ch] [rbp-Dh] BYREF
  _DWORD v14[3]; // [rsp+64h] [rbp-5h] BYREF
  _DWORD *v15; // [rsp+70h] [rbp+7h]
  __int128 Buf1; // [rsp+78h] [rbp+Fh] BYREF

  v15 = a3;
  hKey = 0;
  Buf1 = 0;
  if ( (unsigned __int64)(a1 - 1) <= 0xFFFFFFFFFFFFFFFDuLL && a2 && a4 && a3 )
  {
    if ( (unsigned int)PerflibciGuidFromString(a2, &Buf1) )
    {
      Value = 13;
    }
    else
    {
      v14[2] = *a3;
      v13[1] = 0;
      v14[0] = 0;
      v14[1] = 0;
      v13[0] = 0;
      *(_DWORD *)v10 = 0;
      *(_DWORD *)v11 = 0;
      *(_DWORD *)Data = 0;
      if ( !(unsigned int)PerflibciOpenKey(a1, a2, 131103, &hKey)
        || (Value = PerflibciOpenKey(a1, a2, 131097, &hKey)) == 0 )
      {
        PerflibciQueryValue(hKey, v13);
        v13[0] = 0;
        Value = PerflibciQueryValue(hKey, v14);
        if ( !Value )
          Value = 13;
        operator delete(0);
        operator delete(0);
        PerflibciCloseKey(hKey);
      }
    }
  }
  else
  {
    Value = 87;
  }
  SetLastError(Value);
  return 0;
}

```

## disassembly

```asm
0x18000cc70  mov     [rsp-8+arg_18], rbx
0x18000cc75  push    rbp
0x18000cc76  push    rsi
0x18000cc77  push    rdi
0x18000cc78  push    r12
0x18000cc7a  push    r13
0x18000cc7c  push    r14
0x18000cc7e  push    r15
0x18000cc80  lea     rbp, [rsp-27h]
0x18000cc85  sub     rsp, 90h
0x18000cc8c  mov     rax, cs:__security_cookie
0x18000cc93  xor     rax, rsp
0x18000cc96  mov     [rbp+57h+var_38], rax
0x18000cc9a  xor     r12d, r12d
0x18000cc9d  mov     [rbp+57h+var_50], r8
0x18000cca1  lea     rax, [rcx-1]
0x18000cca5  mov     [rbp+57h+hKey], r12
0x18000cca9  xorps   xmm0, xmm0
0x18000ccac  mov     r13, r9
0x18000ccaf  mov     r15, r8
0x18000ccb2  mov     rdi, rdx
0x18000ccb5  mov     rsi, rcx
0x18000ccb8  mov     ebx, r12d
0x18000ccbb  movups  [rbp+57h+Buf1], xmm0
0x18000ccbf  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000ccc3  ja      loc_18000D11A
0x18000ccc9  test    rdx, rdx
0x18000cccc  jz      loc_18000D11A
0x18000ccd2  test    r9, r9
0x18000ccd5  jz      loc_18000D11A
0x18000ccdb  test    r8, r8
0x18000ccde  jz      loc_18000D11A
0x18000cce4  lea     rdx, [rbp+57h+Buf1]
0x18000cce8  mov     rcx, rdi
0x18000cceb  call    PerflibciGuidFromString
0x18000ccf0  test    eax, eax
0x18000ccf2  jz      short loc_18000CCFE
0x18000ccf4  lea     edi, [r12+0Dh]
0x18000ccf9  jmp     loc_18000D11F
0x18000ccfe  mov     eax, [r15]
0x18000cd01  lea     r9, [rbp+57h+hKey]
0x18000cd05  mov     r8d, 2001Fh
0x18000cd0b  mov     [rbp+57h+var_54], eax
0x18000cd0e  mov     rdx, rdi
0x18000cd11  mov     [rbp+57h+var_80], r12d
0x18000cd15  mov     rcx, rsi
0x18000cd18  mov     [rbp+57h+var_60], r12d
0x18000cd1c  mov     r14d, r12d
0x18000cd1f  mov     [rbp+57h+var_5C], r12d
0x18000cd23  mov     [rbp+57h+var_58], r12d
0x18000cd27  mov     [rbp+57h+var_64], r12d
0x18000cd2b  mov     dword ptr [rbp+57h+var_70], r12d
0x18000cd2f  mov     dword ptr [rbp+57h+var_6C], r12d
0x18000cd33  mov     dword ptr [rbp+57h+Data], r12d
0x18000cd37  call    PerflibciOpenKey
0x18000cd3c  test    eax, eax
0x18000cd3e  jz      short loc_18000CD5F
0x18000cd40  lea     r9, [rbp+57h+hKey]
0x18000cd44  mov     r8d, 20019h
0x18000cd4a  mov     rdx, rdi
0x18000cd4d  mov     rcx, rsi
0x18000cd50  call    PerflibciOpenKey
0x18000cd55  mov     edi, eax
0x18000cd57  test    eax, eax
0x18000cd59  jnz     loc_18000D11F
0x18000cd5f  mov     rcx, [rbp+57h+hKey]; KeyHandle
0x18000cd63  lea     rax, [rbp+57h+var_64]
0x18000cd67  mov     esi, 4
0x18000cd6c  mov     [rsp+0C0h+lpData], rax; void *
0x18000cd71  lea     r9, [rbp+57h+var_7C]
0x18000cd75  mov     [rbp+57h+var_7C], esi
0x18000cd78  lea     r8, [rbp+57h+var_80]
0x18000cd7c  mov     r15, r12
0x18000cd7f  lea     rdx, aInstancetype; "InstanceType"
0x18000cd86  call    PerflibciQueryValue
0x18000cd8b  test    eax, eax
0x18000cd8d  jnz     short loc_18000CD9F
0x18000cd8f  cmp     [rbp+57h+var_80], esi
0x18000cd92  jnz     short loc_18000CD9F
0x18000cd94  mov     esi, [rbp+57h+var_64]
0x18000cd97  mov     [rbp+57h+var_64], esi
0x18000cd9a  lea     esi, [rax+4]
0x18000cd9d  jmp     short loc_18000CDA2
0x18000cd9f  mov     [rbp+57h+var_64], ebx
0x18000cda2  mov     rcx, [rbp+57h+hKey]; KeyHandle
0x18000cda6  lea     rax, [rbp+57h+var_5C]
0x18000cdaa  lea     r9, [rbp+57h+var_7C]
0x18000cdae  mov     [rsp+0C0h+lpData], rax; void *
0x18000cdb3  lea     r8, [rbp+57h+var_80]
0x18000cdb7  mov     [rbp+57h+var_7C], esi
0x18000cdba  lea     rdx, aNameresource; "NameResource"
0x18000cdc1  call    PerflibciQueryValue
0x18000cdc6  mov     edi, eax
0x18000cdc8  test    eax, eax
0x18000cdca  jnz     loc_18000D0FB
0x18000cdd0  cmp     [rbp+57h+var_80], esi
0x18000cdd3  jnz     loc_18000CF8C
0x18000cdd9  mov     rcx, [rbp+57h+hKey]; KeyHandle
0x18000cddd  lea     rax, [rbp+57h+var_58]
0x18000cde1  lea     r9, [rbp+57h+var_7C]
0x18000cde5  mov     [rsp+0C0h+lpData], rax; void *
0x18000cdea  lea     r8, [rbp+57h+var_80]
0x18000cdee  mov     [rbp+57h+var_7C], esi
0x18000cdf1  lea     rdx, aExplainresourc; "ExplainResource"
0x18000cdf8  call    PerflibciQueryValue
0x18000cdfd  mov     edi, eax
0x18000cdff  test    eax, eax
0x18000ce01  jnz     loc_18000D0FB
0x18000ce07  cmp     [rbp+57h+var_80], esi
0x18000ce0a  jnz     loc_18000CF8C
0x18000ce10  mov     rcx, [rbp+57h+hKey]; KeyHandle
0x18000ce14  lea     rax, [rbp+57h+var_70]
0x18000ce18  lea     r9, [rbp+57h+var_7C]
0x18000ce1c  mov     [rsp+0C0h+lpData], rax; void *
0x18000ce21  lea     r8, [rbp+57h+var_80]
0x18000ce25  mov     [rbp+57h+var_7C], esi
0x18000ce28  lea     rdx, aFirstCounter; "First Counter"
0x18000ce2f  call    PerflibciQueryValue
0x18000ce34  or      edi, 0FFFFFFFFh
0x18000ce37  test    eax, eax
0x18000ce39  jnz     short loc_18000CE40
0x18000ce3b  cmp     [rbp+57h+var_80], esi
0x18000ce3e  jz      short loc_18000CE43
0x18000ce40  mov     dword ptr [rbp+57h+var_70], edi
0x18000ce43  mov     rcx, [rbp+57h+hKey]; KeyHandle
0x18000ce47  lea     rax, [rbp+57h+var_6C]
0x18000ce4b  lea     r9, [rbp+57h+var_7C]
0x18000ce4f  mov     [rsp+0C0h+lpData], rax; void *
0x18000ce54  lea     r8, [rbp+57h+var_80]
0x18000ce58  mov     [rbp+57h+var_7C], esi
0x18000ce5b  lea     rdx, aLastCounter; "Last Counter"
0x18000ce62  call    PerflibciQueryValue
0x18000ce67  test    eax, eax
0x18000ce69  jnz     short loc_18000CE70
0x18000ce6b  cmp     [rbp+57h+var_80], esi
0x18000ce6e  jz      short loc_18000CE73
0x18000ce70  mov     dword ptr [rbp+57h+var_6C], edi
0x18000ce73  cmp     dword ptr [r13+20h], 1
0x18000ce78  jnz     loc_18000CF0C
0x18000ce7e  mov     rcx, [rbp+57h+hKey]; KeyHandle
0x18000ce82  lea     r9, [rbp+57h+var_60]
0x18000ce86  lea     r8, [rbp+57h+var_80]
0x18000ce8a  mov     [rsp+0C0h+lpData], r12; void *
0x18000ce8f  lea     rdx, aNeutralname; "NeutralName"
0x18000ce96  call    PerflibciQueryValue
0x18000ce9b  mov     r14d, [rbp+57h+var_60]
0x18000ce9f  mov     edi, eax
0x18000cea1  cmp     eax, 0EAh
0x18000cea6  jnz     short loc_18000CEFA
0x18000cea8  cmp     [rbp+57h+var_80], 1
0x18000ceac  jnz     short loc_18000CEF5
0x18000ceae  cmp     r14d, 0FFFFh
0x18000ceb5  ja      short loc_18000CEEE
0x18000ceb7  mov     rcx, r12; Block
0x18000ceba  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000cebf  lea     ecx, [r14+1]
0x18000cec3  mov     eax, 2
0x18000cec8  shr     rcx, 1
0x18000cecb  mul     rcx
0x18000cece  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000ced5  cmovb   rax, rcx
0x18000ced9  mov     rcx, rax
0x18000cedc  call    ??2@YAPEAX_KUzerofill_t@@@Z; operator new(unsigned __int64,zerofill_t)
0x18000cee1  mov     r12, rax
0x18000cee4  test    rax, rax
0x18000cee7  jnz     short loc_18000CE7E
0x18000cee9  lea     edi, [rax+0Eh]
0x18000ceec  jmp     short loc_18000CEFA
0x18000ceee  mov     edi, 216h
0x18000cef3  jmp     short loc_18000CEFA
0x18000cef5  mov     edi, 0Dh
0x18000cefa  cmp     r14d, 2
0x18000cefe  jb      short loc_18000CF04
0x18000cf00  add     r14d, 0FFFFFFFEh
0x18000cf04  test    edi, edi
0x18000cf06  jnz     loc_18000D0FB
0x18000cf0c  xor     esi, esi
0x18000cf0e  mov     [rbp+57h+var_7C], ebx
0x18000cf11  mov     [rsp+0C0h+lpData], rbx
0x18000cf16  jmp     short loc_18000CF56
0x18000cf18  test    r15, r15
0x18000cf1b  jz      short loc_18000CF25
0x18000cf1d  mov     rcx, r15; Block
0x18000cf20  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000cf25  mov     ecx, [rbp+57h+var_7C]
0x18000cf28  mov     rax, 2492492492492493h
0x18000cf32  mul     rcx
0x18000cf35  mov     esi, ecx
0x18000cf37  sub     rsi, rdx
0x18000cf3a  shr     rsi, 1
0x18000cf3d  add     rsi, rdx
0x18000cf40  shr     rsi, 5
0x18000cf44  call    ??2@YAPEAX_KUzerofill_t@@@Z; operator new(unsigned __int64,zerofill_t)
0x18000cf49  mov     r15, rax
0x18000cf4c  test    rax, rax
0x18000cf4f  jz      short loc_18000CF79
0x18000cf51  mov     [rsp+0C0h+lpData], rax; void *
0x18000cf56  mov     rcx, [rbp+57h+hKey]; KeyHandle
0x18000cf5a  lea     r9, [rbp+57h+var_7C]
0x18000cf5e  lea     r8, [rbp+57h+var_80]
0x18000cf62  lea     rdx, aCounterblock; "CounterBlock"
0x18000cf69  call    PerflibciQueryValue
0x18000cf6e  mov     edi, eax
0x18000cf70  cmp     eax, 0EAh
0x18000cf75  jz      short loc_18000CF18
0x18000cf77  jmp     short loc_18000CF7E
0x18000cf79  mov     edi, 0Eh
0x18000cf7e  test    edi, edi
0x18000cf80  jnz     loc_18000D0FB
0x18000cf86  cmp     [rbp+57h+var_80], 3
0x18000cf8a  jz      short loc_18000CF96
0x18000cf8c  mov     edi, 0Dh
0x18000cf91  jmp     loc_18000D0FB
0x18000cf96  mov     rcx, [rbp+57h+hKey]; KeyHandle
0x18000cf9a  lea     rax, [rbp+57h+Data]
0x18000cf9e  lea     r9, [rbp+57h+var_7C]
0x18000cfa2  mov     [rsp+0C0h+lpData], rax; void *
0x18000cfa7  lea     r8, [rbp+57h+var_80]
0x18000cfab  mov     [rbp+57h+var_7C], 4
0x18000cfb2  lea     rdx, ValueName; "CounterCount"
0x18000cfb9  call    PerflibciQueryValue
0x18000cfbe  mov     edi, eax
0x18000cfc0  test    eax, eax
0x18000cfc2  jnz     short loc_18000CFCA
0x18000cfc4  cmp     [rbp+57h+var_80], 4
0x18000cfc8  jz      short loc_18000CFFA
0x18000cfca  mov     rcx, [rbp+57h+hKey]; hKey
0x18000cfce  lea     rax, [rbp+57h+Data]
0x18000cfd2  mov     [rsp+0C0h+cbData], 4; cbData
0x18000cfda  lea     rdx, ValueName; "CounterCount"
0x18000cfe1  mov     r9d, 4; dwType
0x18000cfe7  mov     [rsp+0C0h+lpData], rax; lpData
0x18000cfec  xor     r8d, r8d; Reserved
0x18000cfef  mov     dword ptr [rbp+57h+Data], esi
0x18000cff2  call    cs:__imp_RegSetValueExW
0x18000cff8  xor     edi, edi
0x18000cffa  mov     r9d, dword ptr [rbp+57h+Data]
0x18000cffe  test    r9d, r9d
0x18000d001  jz      loc_18000D0A4
0x18000d007  mov     eax, dword ptr [rbp+57h+var_70]
0x18000d00a  or      edx, 0FFFFFFFFh
0x18000d00d  cmp     eax, edx
0x18000d00f  jz      short loc_18000D026
0x18000d011  mov     ecx, dword ptr [rbp+57h+var_6C]
0x18000d014  cmp     ecx, edx
0x18000d016  jz      short loc_18000D026
0x18000d018  cmp     ecx, eax
0x18000d01a  jbe     short loc_18000D026
0x18000d01c  sub     ecx, eax
0x18000d01e  lea     eax, [r9+r9]
0x18000d022  cmp     eax, ecx
0x18000d024  jz      short loc_18000D0A4
0x18000d026  mov     edx, [rbp+57h+var_54]
0x18000d029  xor     ecx, ecx
0x18000d02b  mov     eax, edx
0x18000d02d  mov     [rsp+0C0h+cbData], 4; cbData
0x18000d035  and     eax, 0FFFFFFFEh
0x18000d038  cmp     edx, eax
0x18000d03a  setz    cl
0x18000d03d  xor     r8d, r8d; Reserved
0x18000d040  lea     eax, [rcx+1]
0x18000d043  mov     rcx, [rbp+57h+hKey]; hKey
0x18000d047  add     eax, edx
0x18000d049  lea     rdx, aFirstCounter; "First Counter"
0x18000d050  mov     dword ptr [rbp+57h+var_70], eax
0x18000d053  lea     ebx, [rax+r9*2]
0x18000d057  mov     r9d, 4; dwType
0x18000d05d  lea     rax, [rbp+57h+var_70]
0x18000d061  mov     dword ptr [rbp+57h+var_6C], ebx
0x18000d064  mov     [rsp+0C0h+lpData], rax; lpData
0x18000d069  call    cs:__imp_RegSetValueExW
0x18000d06f  mov     rcx, [rbp+57h+hKey]; hKey
0x18000d073  lea     rax, [rbp+57h+var_6C]
0x18000d077  mov     [rsp+0C0h+cbData], 4; cbData
0x18000d07f  lea     rdx, aLastCounter; "Last Counter"
0x18000d086  mov     r9d, 4; dwType
0x18000d08c  mov     [rsp+0C0h+lpData], rax; lpData
0x18000d091  xor     r8d, r8d; Reserved
0x18000d094  call    cs:__imp_RegSetValueExW
0x18000d09a  mov     rax, [rbp+57h+var_50]
0x18000d09e  mov     r9d, dword ptr [rbp+57h+Data]
0x18000d0a2  mov     [rax], ebx
0x18000d0a4  mov     [rsp+0C0h+var_90], 1; int
0x18000d0ac  lea     rcx, [rbp+57h+Buf1]; Buf1
0x18000d0b0  imul    r8d, esi, 38h ; '8'
0x18000d0b4  mov     rdx, r15
0x18000d0b7  mov     word ptr [rsp+0C0h+cbData], r14w; __int16
0x18000d0bd  mov     [rsp+0C0h+lpData], r12; void *
0x18000d0c2  call    PerflibciCreateOrFindCounterSet
0x18000d0c7  mov     rbx, rax
0x18000d0ca  test    rax, rax
0x18000d0cd  jnz     short loc_18000D0D9
0x18000d0cf  call    cs:__imp_GetLastError
0x18000d0d5  mov     edi, eax
0x18000d0d7  jmp     short loc_18000D0FB
0x18000d0d9  mov     [rax+10h], r13
0x18000d0dd  mov     eax, [rbp+57h+var_5C]
0x18000d0e0  mov     [rbx+50h], eax
0x18000d0e3  mov     eax, [rbp+57h+var_58]
0x18000d0e6  mov     [rbx+54h], eax
  ... truncated ...
```
