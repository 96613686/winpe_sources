# DllGetActivationFactory

- ea: `0x18001eed0`
- end: `0x18001f09d`
- name: `DllGetActivationFactory`
- size: `461`
- prototype: `__int64 __fastcall(HSTRING string)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x18001e530`
- `0x18001eed0`
- `0x1800cbde0`
- `0x180136810`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x18001ef46`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x18001ef46`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001ef6a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001ef6a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18001ef2a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18001ef2a`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18001effb`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18001effb`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x18001f068`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x18001f068`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18001ef0b`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18001ef0b`

## pseudocode

```c
__int64 __fastcall DllGetActivationFactory(HSTRING string, _QWORD *a2)
{
  PCWSTR StringRawBuffer; // rbp
  unsigned __int64 v5; // rbx
  unsigned __int64 v6; // rdi
  __int64 v7; // rax
  unsigned __int16 *v8; // rcx
  __int64 v9; // rax
  int v10; // edx
  int v11; // r8d
  BOOL hasEmbedNull; // [rsp+30h] [rbp-58h] BYREF
  int v14; // [rsp+34h] [rbp-54h] BYREF
  __int128 v15; // [rsp+38h] [rbp-50h] BYREF
  _BYTE v16[22]; // [rsp+48h] [rbp-40h]

  InitOnceExecuteOnce(&InitOnce, InitFn, 0, 0);
  byte_180163AA8 = 1;
  *a2 = 0;
  hasEmbedNull = 0;
  if ( WindowsIsStringEmpty(string) || WindowsStringHasEmbeddedNull(string, &hasEmbedNull) < 0 || hasEmbedNull )
  {
    v15 = xmmword_1801434D0;
    *(_OWORD *)v16 = xmmword_1801434E0;
    *(_QWORD *)&v16[14] = 0x6400490073LL;
    RoOriginateErrorW(2147942487LL, 18, &v15);
    return 2147942487LL;
  }
  else
  {
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v5 = (*(__int64 (__fastcall **)(__int64 *))(qword_180163AA0 + 40))(&qword_180163AA0) + 8;
    v6 = (*(__int64 (__fastcall **)(__int64 *))(qword_180163AA0 + 48))(&qword_180163AA0);
    if ( v5 >= v6 )
    {
LABEL_11:
      RoOriginateError(2147746065LL, string);
      return 2147746065LL;
    }
    else
    {
      while ( 1 )
      {
        if ( *(_QWORD *)v5 )
        {
          v7 = (*(__int64 (**)(void))(*(_QWORD *)v5 + 8LL))();
          v8 = (unsigned __int16 *)StringRawBuffer;
          v9 = v7 - (_QWORD)StringRawBuffer;
          do
          {
            v10 = *(unsigned __int16 *)((char *)v8 + v9);
            v11 = *v8 - v10;
            if ( v11 )
              break;
            ++v8;
          }
          while ( v10 );
          if ( !v11 )
            break;
        }
        v5 += 8LL;
        if ( v5 >= v6 )
          goto LABEL_11;
      }
      v14 = 1;
      return sub_18001E530((unsigned int)&qword_180163AA0, (unsigned int)&v14, 0, *(_QWORD *)v5, (__int64)a2);
    }
  }
}

```

## disassembly

```asm
0x18001eed0  mov     [rsp+arg_10], rbx
0x18001eed5  mov     [rsp+arg_18], rbp
0x18001eeda  push    rsi
0x18001eedb  push    rdi
0x18001eedc  push    r14
0x18001eede  sub     rsp, 70h
0x18001eee2  mov     rax, cs:__security_cookie
0x18001eee9  xor     rax, rsp
0x18001eeec  mov     [rsp+88h+var_28], rax
0x18001eef1  mov     r14, rdx
0x18001eef4  mov     rsi, rcx
0x18001eef7  xor     r9d, r9d; Context
0x18001eefa  xor     r8d, r8d; Parameter
0x18001eefd  lea     rdx, InitFn; InitFn
0x18001ef04  lea     rcx, InitOnce; InitOnce
0x18001ef0b  call    cs:InitOnceExecuteOnce
0x18001ef12  nop     dword ptr [rax+rax+00h]
0x18001ef17  mov     cs:byte_180163AA8, 1
0x18001ef1e  xor     eax, eax
0x18001ef20  mov     [r14], rax
0x18001ef23  mov     [rsp+88h+hasEmbedNull], eax
0x18001ef27  mov     rcx, rsi; string
0x18001ef2a  call    cs:WindowsIsStringEmpty
0x18001ef31  nop     dword ptr [rax+rax+00h]
0x18001ef36  test    eax, eax
0x18001ef38  jnz     loc_18001F033
0x18001ef3e  lea     rdx, [rsp+88h+hasEmbedNull]; hasEmbedNull
0x18001ef43  mov     rcx, rsi; string
0x18001ef46  call    cs:WindowsStringHasEmbeddedNull
0x18001ef4d  nop     dword ptr [rax+rax+00h]
0x18001ef52  test    eax, eax
0x18001ef54  js      loc_18001F033
0x18001ef5a  cmp     [rsp+88h+hasEmbedNull], 1
0x18001ef5f  jz      loc_18001F033
0x18001ef65  xor     edx, edx; length
0x18001ef67  mov     rcx, rsi; string
0x18001ef6a  call    cs:WindowsGetStringRawBuffer
0x18001ef71  nop     dword ptr [rax+rax+00h]
0x18001ef76  mov     rbp, rax
0x18001ef79  mov     rcx, cs:qword_180163AA0
0x18001ef80  mov     rax, [rcx+28h]
0x18001ef84  lea     rcx, qword_180163AA0
0x18001ef8b  call    cs:__guard_dispatch_icall_fptr
0x18001ef91  lea     rbx, [rax+8]
0x18001ef95  mov     rcx, cs:qword_180163AA0
0x18001ef9c  mov     rax, [rcx+30h]
0x18001efa0  lea     rcx, qword_180163AA0
0x18001efa7  call    cs:__guard_dispatch_icall_fptr
0x18001efad  mov     rdi, rax
0x18001efb0  cmp     rbx, rax
0x18001efb3  jnb     short loc_18001EFF3
0x18001efb5  mov     rax, [rbx]
0x18001efb8  test    rax, rax
0x18001efbb  jz      short loc_18001EFEA
0x18001efbd  mov     rax, [rax+8]
0x18001efc1  call    cs:__guard_dispatch_icall_fptr
0x18001efc7  mov     rcx, rbp
0x18001efca  sub     rax, rbp
0x18001efcd  nop     dword ptr [rax]
0x18001efd0  movzx   r8d, word ptr [rcx]
0x18001efd4  movzx   edx, word ptr [rcx+rax]
0x18001efd8  sub     r8d, edx
0x18001efdb  jnz     short loc_18001EFE5
0x18001efdd  add     rcx, 2
0x18001efe1  test    edx, edx
0x18001efe3  jnz     short loc_18001EFD0
0x18001efe5  test    r8d, r8d
0x18001efe8  jz      short loc_18001F00F
0x18001efea  add     rbx, 8
0x18001efee  cmp     rbx, rdi
0x18001eff1  jb      short loc_18001EFB5
0x18001eff3  mov     rdx, rsi
0x18001eff6  mov     ecx, 80040111h
0x18001effb  call    cs:RoOriginateError
0x18001f002  nop     dword ptr [rax+rax+00h]
0x18001f007  nop
0x18001f008  mov     eax, 80040111h
0x18001f00d  jmp     short loc_18001F07A
0x18001f00f  mov     [rsp+88h+var_54], 1
0x18001f017  mov     [rsp+88h+var_68], r14
0x18001f01c  mov     r9, [rbx]
0x18001f01f  lea     rdx, [rsp+88h+var_54]
0x18001f024  lea     rcx, qword_180163AA0
0x18001f02b  call    sub_18001E530
0x18001f030  nop
0x18001f031  jmp     short loc_18001F07A
0x18001f033  movups  xmm0, cs:xmmword_1801434D0
0x18001f03a  movups  [rsp+88h+var_50], xmm0
0x18001f03f  movups  xmm1, cs:xmmword_1801434E0
0x18001f046  movups  xmmword ptr [rsp+88h+var_40], xmm1
0x18001f04b  movsd   xmm0, qword ptr cs:xmmword_1801434E0+0Eh
0x18001f053  movsd   qword ptr [rsp+88h+var_40+0Eh], xmm0
0x18001f059  lea     r8, [rsp+88h+var_50]
0x18001f05e  mov     edx, 12h
0x18001f063  mov     ecx, 80070057h
0x18001f068  call    cs:RoOriginateErrorW
0x18001f06f  nop     dword ptr [rax+rax+00h]
0x18001f074  nop
0x18001f075  mov     eax, 80070057h
0x18001f07a  mov     rcx, [rsp+88h+var_28]
0x18001f07f  xor     rcx, rsp; StackCookie
0x18001f082  call    __security_check_cookie
0x18001f087  lea     r11, [rsp+88h+var_18]
0x18001f08c  mov     rbx, [r11+30h]
0x18001f090  mov     rbp, [r11+38h]
0x18001f094  mov     rsp, r11
0x18001f097  pop     r14
0x18001f099  pop     rdi
0x18001f09a  pop     rsi
0x18001f09b  retn
```
