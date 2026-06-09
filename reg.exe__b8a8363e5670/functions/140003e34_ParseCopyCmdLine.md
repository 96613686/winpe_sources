# ParseCopyCmdLine

- ea: `0x140003e34`
- end: `0x1400040af`
- name: `ParseCopyCmdLine`
- size: `635`
- prototype: `__int64 __fastcall(unsigned int, PCNZWCH *, int *, int *, _DWORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1400038f8`

## callees

- `0x140001e90`
- `0x140002ce4`
- `0x140003e34`
- `0x14000d694`
- `0x14000d990`
- `0x14000e600`
- `0x14000ee5c`
- `0x14000eecc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140003ec1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140003ec1`

## pseudocode

```c
__int64 __fastcall ParseCopyCmdLine(unsigned int a1, PCNZWCH *a2, int *a3, int *a4, _DWORD *a5)
{
  __int64 v10; // rcx
  __int64 ResString2FromModule; // rax
  unsigned int v12; // r14d

  if ( !a1 || !a2 || !a3 || !a4 || !a5 || (unsigned int)*a3 > 0xB )
    goto LABEL_36;
  if ( a1 >= 3 && (unsigned int)InString(a2[2], L"-?|/?|-h|/h") == 1 )
  {
    if ( a1 == 3 )
    {
      *a5 = 1;
      return 1;
    }
    goto LABEL_12;
  }
  if ( a1 - 4 > 3 )
  {
LABEL_12:
    SetLastError(0x800401E4);
    ResString2FromModule = GetResString2FromModule(v10, 103, 0);
    SetReason2(1, ResString2FromModule, L"COPY");
    return 0;
  }
  if ( (unsigned int)StringCompareExW(a2[1], L"COPY") )
  {
LABEL_36:
    SaveErrorMessage(87);
    return 0;
  }
  if ( (unsigned int)BreakDownKeyString(a2[2], a3) && (unsigned int)BreakDownKeyString(a2[3], a4) )
  {
    v12 = 4;
    if ( a1 > 4 )
    {
      while ( 1 )
      {
        if ( (unsigned int)StringCompareExW(a2[v12], L"/f") && (unsigned int)StringCompareExW(a2[v12], L"-f") )
        {
          if ( (unsigned int)StringCompareW(a2[v12], L"/s") && (unsigned int)StringCompareW(a2[v12], L"-s") )
          {
            if ( (unsigned int)StringCompareExW(a2[v12], L"/reg:32")
              && (unsigned int)StringCompareExW(a2[v12], L"-reg:32") )
            {
              if ( (unsigned int)StringCompareExW(a2[v12], L"/reg:64")
                && (unsigned int)StringCompareExW(a2[v12], L"-reg:64")
                || a3[35] )
              {
                goto LABEL_12;
              }
              a3[35] = 256;
              a4[35] = 256;
            }
            else
            {
              if ( a3[35] )
                goto LABEL_12;
              a3[35] = 512;
              a4[35] = 512;
            }
          }
          else
          {
            if ( a3[8] == 1 )
              goto LABEL_12;
            a3[8] = 1;
          }
        }
        else
        {
          if ( a3[6] == 1 )
            goto LABEL_12;
          a3[6] = 1;
        }
        if ( ++v12 >= a1 )
          return 1;
      }
    }
    return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x140003e34  push    rbx
0x140003e36  push    rbp
0x140003e37  push    rsi
0x140003e38  push    rdi
0x140003e39  push    r12
0x140003e3b  push    r14
0x140003e3d  push    r15
0x140003e3f  sub     rsp, 20h
0x140003e43  mov     r15, r9
0x140003e46  mov     rbx, r8
0x140003e49  mov     rdi, rdx
0x140003e4c  mov     esi, ecx
0x140003e4e  test    ecx, ecx
0x140003e50  jz      loc_140004093
0x140003e56  test    rdx, rdx
0x140003e59  jz      loc_140004093
0x140003e5f  test    rbx, rbx
0x140003e62  jz      loc_140004093
0x140003e68  test    r9, r9
0x140003e6b  jz      loc_140004093
0x140003e71  mov     r14, [rsp+58h+arg_20]
0x140003e79  test    r14, r14
0x140003e7c  jz      loc_140004093
0x140003e82  cmp     dword ptr [r8], 0Bh
0x140003e86  ja      loc_140004093
0x140003e8c  mov     r12d, 1
0x140003e92  cmp     ecx, 3
0x140003e95  jb      short loc_140003EF0
0x140003e97  mov     rcx, [rdi+10h]; lpString
0x140003e9b  lea     rdx, aHH; "-?|/?|-h|/h"
0x140003ea2  call    InString
0x140003ea7  cmp     eax, r12d
0x140003eaa  jnz     short loc_140003EF0
0x140003eac  cmp     esi, 3
0x140003eaf  jnz     short loc_140003EBC
0x140003eb1  mov     [r14], r12d
0x140003eb4  mov     eax, r12d
0x140003eb7  jmp     loc_14000409F
0x140003ebc  mov     ecx, 800401E4h; dwErrCode
0x140003ec1  call    cs:__imp_SetLastError
0x140003ec8  nop     dword ptr [rax+rax+00h]
0x140003ecd  xor     r8d, r8d
0x140003ed0  lea     edx, [r8+67h]
0x140003ed4  call    GetResString2FromModule
0x140003ed9  lea     r8, aCopy_0; "COPY"
0x140003ee0  mov     rdx, rax
0x140003ee3  mov     ecx, r12d
0x140003ee6  call    SetReason2
0x140003eeb  jmp     loc_14000409D
0x140003ef0  lea     eax, [rsi-4]
0x140003ef3  cmp     eax, 3
0x140003ef6  ja      short loc_140003EBC
0x140003ef8  mov     rcx, [rdi+8]; lpString1
0x140003efc  lea     rdx, aCopy; "COPY"
0x140003f03  xor     r9d, r9d
0x140003f06  call    StringCompareExW
0x140003f0b  test    eax, eax
0x140003f0d  jnz     loc_140004093
0x140003f13  mov     rcx, [rdi+10h]
0x140003f17  mov     rdx, rbx
0x140003f1a  call    BreakDownKeyString
0x140003f1f  test    eax, eax
0x140003f21  jz      loc_14000409D
0x140003f27  mov     rcx, [rdi+18h]
0x140003f2b  mov     rdx, r15
0x140003f2e  call    BreakDownKeyString
0x140003f33  test    eax, eax
0x140003f35  jz      loc_14000409D
0x140003f3b  mov     r14d, 4
0x140003f41  cmp     esi, r14d
0x140003f44  jbe     loc_140003EB4
0x140003f4a  mov     ebp, r14d
0x140003f4d  lea     rdx, asc_140011CFC; "/f"
0x140003f54  xor     r9d, r9d
0x140003f57  mov     rcx, [rdi+rbp*8]; lpString1
0x140003f5b  call    StringCompareExW
0x140003f60  test    eax, eax
0x140003f62  jz      loc_140004074
0x140003f68  mov     rcx, [rdi+rbp*8]; lpString1
0x140003f6c  lea     rdx, asc_140011D04; "-f"
0x140003f73  xor     r9d, r9d
0x140003f76  call    StringCompareExW
0x140003f7b  test    eax, eax
0x140003f7d  jz      loc_140004074
0x140003f83  mov     rcx, [rdi+rbp*8]; lpString1
0x140003f87  lea     rdx, aS_4; "/s"
0x140003f8e  xor     r9d, r9d
0x140003f91  mov     r8d, r12d
0x140003f94  call    StringCompareW
0x140003f99  test    eax, eax
0x140003f9b  jz      loc_140004064
0x140003fa1  mov     rcx, [rdi+rbp*8]; lpString1
0x140003fa5  lea     rdx, aS_3; "-s"
0x140003fac  xor     r9d, r9d
0x140003faf  mov     r8d, r12d
0x140003fb2  call    StringCompareW
0x140003fb7  test    eax, eax
0x140003fb9  jz      loc_140004064
0x140003fbf  mov     rcx, [rdi+rbp*8]; lpString1
0x140003fc3  lea     rdx, aReg32; "/reg:32"
0x140003fca  xor     r9d, r9d
0x140003fcd  call    StringCompareExW
0x140003fd2  test    eax, eax
0x140003fd4  jz      short loc_140004043
0x140003fd6  mov     rcx, [rdi+rbp*8]; lpString1
0x140003fda  lea     rdx, aReg32_0; "-reg:32"
0x140003fe1  xor     r9d, r9d
0x140003fe4  call    StringCompareExW
0x140003fe9  test    eax, eax
0x140003feb  jz      short loc_140004043
0x140003fed  mov     rcx, [rdi+rbp*8]; lpString1
0x140003ff1  lea     rdx, aReg64_0; "/reg:64"
0x140003ff8  xor     r9d, r9d
0x140003ffb  call    StringCompareExW
0x140004000  test    eax, eax
0x140004002  jz      short loc_14000401F
0x140004004  mov     rcx, [rdi+rbp*8]; lpString1
0x140004008  lea     rdx, aReg64; "-reg:64"
0x14000400f  xor     r9d, r9d
0x140004012  call    StringCompareExW
0x140004017  test    eax, eax
0x140004019  jnz     loc_140003EBC
0x14000401f  cmp     dword ptr [rbx+8Ch], 0
0x140004026  jnz     loc_140003EBC
0x14000402c  mov     dword ptr [rbx+8Ch], 100h
0x140004036  mov     dword ptr [r15+8Ch], 100h
0x140004041  jmp     short loc_140004082
0x140004043  cmp     dword ptr [rbx+8Ch], 0
0x14000404a  jnz     loc_140003EBC
0x140004050  mov     eax, 200h
0x140004055  mov     [rbx+8Ch], eax
0x14000405b  mov     [r15+8Ch], eax
0x140004062  jmp     short loc_140004082
0x140004064  cmp     [rbx+20h], r12d
0x140004068  jz      loc_140003EBC
0x14000406e  mov     [rbx+20h], r12d
0x140004072  jmp     short loc_140004082
0x140004074  cmp     [rbx+18h], r12d
0x140004078  jz      loc_140003EBC
0x14000407e  mov     [rbx+18h], r12d
0x140004082  add     r14d, r12d
0x140004085  cmp     r14d, esi
0x140004088  jb      loc_140003F4A
0x14000408e  jmp     loc_140003EB4
0x140004093  mov     ecx, 57h ; 'W'
0x140004098  call    SaveErrorMessage
0x14000409d  xor     eax, eax
0x14000409f  add     rsp, 20h
0x1400040a3  pop     r15
0x1400040a5  pop     r14
0x1400040a7  pop     r12
0x1400040a9  pop     rdi
0x1400040aa  pop     rsi
0x1400040ab  pop     rbp
0x1400040ac  pop     rbx
0x1400040ad  retn
```
