# LdrpAppxGetRemediationRegistryKey

- ea: `0x1801368a4`
- end: `0x180136a45`
- name: `LdrpAppxGetRemediationRegistryKey`
- size: `417`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, registry_config, broker_com_uri`

## callers

- `0x180091650`

## callees

- `0x180016bc0`
- `0x1800ca97c`
- `0x1800e8d1c`
- `0x1801368a4`
- `0x180160820`
- `0x180162000`

## string_xrefs

- `0x1801368fb`: `TargetNtPath`
- `0x1801368de`: `\Registry\Machine\Software\Microsoft\Windows\CurrentVersion\AppModel\StateChange`

## pseudocode

```c
__int64 __fastcall LdrpAppxGetRemediationRegistryKey(int a1, __int64 a2, __int64 a3)
{
  __int64 result; // rax
  __int64 v7; // rdx
  __int64 v8; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v9; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v10[48]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v11[528]; // [rsp+90h] [rbp-70h] BYREF

  memset(v10, 0, 44);
  v9 = 0;
  result = RtlGetPersistedStateLocation((wchar_t *)L"AppxStateChange", v11, 522, (__int64)&v8);
  if ( (int)result >= 0 )
  {
    if ( a1 != -1073740702 )
    {
      DWORD1(v9) = 0;
      v8 = 0;
      result = RtlStringLengthWorkerW_0(v11, 0x7FFF, &v8);
      if ( (int)result < 0 )
        return result;
      v7 = 131097;
      goto LABEL_9;
    }
    result = RtlStringCbCatW(v11, 522, L"\\PackageList\\");
    if ( (int)result >= 0 )
    {
      result = RtlStringCbCatW(v11, 522, a2);
      if ( (int)result >= 0 )
      {
        DWORD1(v9) = 0;
        v8 = 0;
        result = RtlStringLengthWorkerW_0(v11, 0x7FFF, &v8);
        if ( (int)result >= 0 )
        {
          v7 = 131353;
LABEL_9:
          *(_DWORD *)v10 = 48;
          LOWORD(v9) = 2 * v8;
          *(_QWORD *)&v10[8] = 0;
          WORD1(v9) = 2 * v8 + 2;
          *(_DWORD *)&v10[24] = 64;
          *((_QWORD *)&v9 + 1) = v11;
          *(_QWORD *)&v10[16] = &v9;
          *(_OWORD *)&v10[32] = 0;
          return NtOpenKeyEx(a3, v7, v10, 0);
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1801368a4  mov     [rsp-8+arg_0], rbx
0x1801368a9  push    rbp
0x1801368aa  push    rsi
0x1801368ab  push    rdi
0x1801368ac  lea     rbp, [rsp-1B0h]
0x1801368b4  sub     rsp, 2B0h
0x1801368bb  mov     rax, cs:__security_cookie
0x1801368c2  xor     rax, rsp
0x1801368c5  mov     [rbp+1C0h+var_20], rax
0x1801368cc  xorps   xmm0, xmm0
0x1801368cf  xor     eax, eax
0x1801368d1  lea     rax, [rsp+2C0h+var_280]
0x1801368d6  mov     rsi, r8
0x1801368d9  mov     [rsp+2C0h+var_290], rax; __int64
0x1801368de  lea     r8, aRegistryMachin_34; "\\Registry\\Machine\\Software\\Microsof"...
0x1801368e5  lea     rax, [rbp+1C0h+var_230]
0x1801368e9  mov     [rsp+2C0h+var_298], 20Ah; int
0x1801368f1  mov     rdi, rdx
0x1801368f4  mov     [rsp+2C0h+var_2A0], rax; void *
0x1801368f9  mov     ebx, ecx
0x1801368fb  lea     rdx, aTargetntpath; "TargetNtPath"
0x180136902  movups  [rsp+2C0h+var_258], xmm0
0x180136907  xor     r9d, r9d
0x18013690a  lea     rcx, aAppxstatechang; "AppxStateChange"
0x180136911  movups  [rsp+2C0h+var_268], xmm0
0x180136916  movups  [rsp+2C0h+var_258+0Ch], xmm0
0x18013691b  movups  [rsp+2C0h+var_278], xmm0
0x180136920  call    RtlGetPersistedStateLocation
0x180136925  test    eax, eax
0x180136927  js      loc_180136A22
0x18013692d  lea     rcx, [rbp+1C0h+var_230]
0x180136931  cmp     ebx, 0C0000462h
0x180136937  jnz     short loc_18013699E
0x180136939  lea     r8, aPackagelist; "\\PackageList\\"
0x180136940  mov     edx, 20Ah
0x180136945  call    RtlStringCbCatW
0x18013694a  test    eax, eax
0x18013694c  js      loc_180136A22
0x180136952  mov     r8, rdi
0x180136955  lea     rcx, [rbp+1C0h+var_230]
0x180136959  mov     edx, 20Ah
0x18013695e  call    RtlStringCbCatW
0x180136963  test    eax, eax
0x180136965  js      loc_180136A22
0x18013696b  lea     r8, [rsp+2C0h+var_280]
0x180136970  mov     dword ptr [rsp+2C0h+var_278+4], 0
0x180136978  mov     edx, 7FFFh
0x18013697d  mov     [rsp+2C0h+var_280], 0
0x180136986  lea     rcx, [rbp+1C0h+var_230]
0x18013698a  call    RtlStringLengthWorkerW_0
0x18013698f  test    eax, eax
0x180136991  js      loc_180136A22
0x180136997  mov     edx, 20119h
0x18013699c  jmp     short loc_1801369C7
0x18013699e  lea     r8, [rsp+2C0h+var_280]
0x1801369a3  mov     dword ptr [rsp+2C0h+var_278+4], 0
0x1801369ab  mov     edx, 7FFFh
0x1801369b0  mov     [rsp+2C0h+var_280], 0
0x1801369b9  call    RtlStringLengthWorkerW_0
0x1801369be  test    eax, eax
0x1801369c0  js      short loc_180136A22
0x1801369c2  mov     edx, 20019h
0x1801369c7  movzx   eax, word ptr [rsp+2C0h+var_280]
0x1801369cc  lea     r8, [rsp+2C0h+var_268]
0x1801369d1  add     ax, ax
0x1801369d4  mov     dword ptr [rsp+2C0h+var_268], 30h ; '0'
0x1801369dc  mov     word ptr [rsp+2C0h+var_278], ax
0x1801369e1  xorps   xmm0, xmm0
0x1801369e4  add     ax, 2
0x1801369e8  mov     qword ptr [rsp+2C0h+var_268+8], 0
0x1801369f1  mov     word ptr [rsp+2C0h+var_278+2], ax
0x1801369f6  xor     r9d, r9d
0x1801369f9  lea     rax, [rbp+1C0h+var_230]
0x1801369fd  mov     dword ptr [rsp+2C0h+var_258+8], 40h ; '@'
0x180136a05  mov     qword ptr [rsp+2C0h+var_278+8], rax
0x180136a0a  mov     rcx, rsi
0x180136a0d  lea     rax, [rsp+2C0h+var_278]
0x180136a12  mov     qword ptr [rsp+2C0h+var_258], rax
0x180136a17  movdqu  [rsp+2C0h+var_248], xmm0
0x180136a1d  call    NtOpenKeyEx
0x180136a22  mov     rcx, [rbp+1C0h+var_20]
0x180136a29  xor     rcx, rsp; StackCookie
0x180136a2c  call    __security_check_cookie
0x180136a31  mov     rbx, [rsp+2C0h+arg_0]
0x180136a39  add     rsp, 2B0h
0x180136a40  pop     rdi
0x180136a41  pop     rsi
0x180136a42  pop     rbp
0x180136a43  retn
```
