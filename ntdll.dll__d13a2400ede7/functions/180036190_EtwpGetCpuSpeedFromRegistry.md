# EtwpGetCpuSpeedFromRegistry

- ea: `0x180036190`
- end: `0x1800362d3`
- name: `EtwpGetCpuSpeedFromRegistry`
- size: `323`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180034bd0`
- `0x180036680`

## callees

- `0x180036190`
- `0x18012d320`
- `0x18015ecc0`
- `0x18015ed20`
- `0x18015edc0`
- `0x180162810`

## string_xrefs

- `0x1800361c5`: `\Registry\Machine\HARDWARE\DESCRIPTION\System\CentralProcessor\0`

## pseudocode

```c
__int64 __fastcall EtwpGetCpuSpeedFromRegistry(_DWORD *a1)
{
  size_t v2; // rax
  __int64 result; // rax
  size_t v4; // rax
  int v5; // ebx
  int v6; // [rsp+30h] [rbp-49h] BYREF
  HANDLE Handle; // [rsp+38h] [rbp-41h] BYREF
  __int128 v8; // [rsp+40h] [rbp-39h] BYREF
  _QWORD v9[2]; // [rsp+50h] [rbp-29h] BYREF
  _DWORD v10[2]; // [rsp+60h] [rbp-19h] BYREF
  __int64 v11; // [rsp+68h] [rbp-11h]
  _QWORD *v12; // [rsp+70h] [rbp-9h]
  int v13; // [rsp+78h] [rbp-1h]
  _BYTE v14[20]; // [rsp+7Ch] [rbp+3h]
  __int128 v15; // [rsp+90h] [rbp+17h] BYREF

  v6 = 0;
  Handle = 0;
  v12 = 0;
  v9[1] = L"\\Registry\\Machine\\HARDWARE\\DESCRIPTION\\System\\CentralProcessor\\0";
  *(_OWORD *)v14 = 0;
  v9[0] = 0;
  v8 = 0;
  v10[1] = 0;
  v15 = 0;
  v2 = 2 * wcslen(L"\\Registry\\Machine\\HARDWARE\\DESCRIPTION\\System\\CentralProcessor\\0");
  v10[0] = 48;
  v11 = 0;
  v13 = 64;
  if ( v2 >= 0xFFFE )
    LOWORD(v2) = -4;
  LOWORD(v9[0]) = v2;
  WORD1(v9[0]) = v2 + 2;
  v12 = v9;
  *(_OWORD *)&v14[4] = 0;
  result = NtOpenKey(&Handle, 131097, v10);
  if ( (int)result >= 0 )
  {
    *(_QWORD *)&v8 = 0;
    *((_QWORD *)&v8 + 1) = L"~MHz";
    v4 = 2 * wcslen(L"~MHz");
    if ( v4 >= 0xFFFE )
      LOWORD(v4) = -4;
    LOWORD(v8) = v4;
    WORD1(v8) = v4 + 2;
    v5 = NtQueryValueKey(Handle, &v8, 2, &v15, 16, &v6);
    if ( v5 >= 0 )
      *a1 = HIDWORD(v15);
    NtClose(Handle);
    return (unsigned int)v5;
  }
  return result;
}

```

## disassembly

```asm
0x180036190  push    rbp
0x180036192  push    rbx
0x180036193  push    rdi
0x180036194  push    r15
0x180036196  lea     rbp, [rsp-3Fh]
0x18003619b  sub     rsp, 0B8h
0x1800361a2  mov     rax, cs:__security_cookie
0x1800361a9  xor     rax, rsp
0x1800361ac  mov     [rbp+57h+var_30], rax
0x1800361b0  xorps   xmm0, xmm0
0x1800361b3  mov     [rbp+57h+var_A0], 0
0x1800361ba  mov     rdi, rcx
0x1800361bd  mov     [rbp+57h+Handle], 0
0x1800361c5  lea     rcx, aRegistryMachin_20; "\\Registry\\Machine\\HARDWARE\\DESCRIPT"...
0x1800361cc  xor     eax, eax
0x1800361ce  movups  [rbp+57h+var_60], xmm0
0x1800361d2  mov     [rbp+57h+var_78], rcx
0x1800361d6  movups  [rbp+57h+var_60+0Ch], xmm0
0x1800361da  mov     [rbp+57h+var_80], rax
0x1800361de  movups  [rbp+57h+var_90], xmm0
0x1800361e2  movups  [rbp+57h+var_70], xmm0
0x1800361e6  movups  [rbp+57h+var_40], xmm0
0x1800361ea  call    wcslen
0x1800361ef  add     rax, rax
0x1800361f2  mov     dword ptr [rbp+57h+var_70], 30h ; '0'
0x1800361f9  cmp     rax, 0FFFEh
0x1800361ff  mov     qword ptr [rbp+57h+var_70+8], 0
0x180036207  xorps   xmm0, xmm0
0x18003620a  mov     dword ptr [rbp+57h+var_60+8], 40h ; '@'
0x180036211  mov     r15d, 0FFFCh
0x180036217  lea     r8, [rbp+57h+var_70]
0x18003621b  cmovnb  rax, r15
0x18003621f  lea     rcx, [rbp+57h+Handle]
0x180036223  mov     word ptr [rbp+57h+var_80], ax
0x180036227  mov     ebx, 2
0x18003622c  add     ax, bx
0x18003622f  mov     edx, 20019h
0x180036234  mov     word ptr [rbp+57h+var_80+2], ax
0x180036238  lea     rax, [rbp+57h+var_80]
0x18003623c  mov     qword ptr [rbp+57h+var_60], rax
0x180036240  movdqu  [rbp+57h+var_50], xmm0
0x180036245  call    NtOpenKey
0x18003624a  test    eax, eax
0x18003624c  js      short loc_1800362B9
0x18003624e  lea     rcx, aMhz; "~MHz"
0x180036255  mov     qword ptr [rbp+57h+var_90], 0
0x18003625d  mov     qword ptr [rbp+57h+var_90+8], rcx
0x180036261  call    wcslen
0x180036266  mov     rcx, [rbp+57h+Handle]
0x18003626a  lea     r9, [rbp+57h+var_40]
0x18003626e  add     rax, rax
0x180036271  lea     rdx, [rbp+57h+var_90]
0x180036275  cmp     rax, 0FFFEh
0x18003627b  mov     r8d, ebx
0x18003627e  cmovnb  rax, r15
0x180036282  mov     word ptr [rbp+57h+var_90], ax
0x180036286  add     ax, bx
0x180036289  mov     word ptr [rbp+57h+var_90+2], ax
0x18003628d  lea     rax, [rbp+57h+var_A0]
0x180036291  mov     [rsp+0D0h+var_A8], rax
0x180036296  mov     [rsp+0D0h+var_B0], 10h
0x18003629e  call    NtQueryValueKey
0x1800362a3  mov     ebx, eax
0x1800362a5  test    eax, eax
0x1800362a7  js      short loc_1800362AE
0x1800362a9  mov     ecx, dword ptr [rbp+57h+var_40+0Ch]
0x1800362ac  mov     [rdi], ecx
0x1800362ae  mov     rcx, [rbp+57h+Handle]; Handle
0x1800362b2  call    NtClose
0x1800362b7  mov     eax, ebx
0x1800362b9  mov     rcx, [rbp+57h+var_30]
0x1800362bd  xor     rcx, rsp; StackCookie
0x1800362c0  call    __security_check_cookie
0x1800362c5  add     rsp, 0B8h
0x1800362cc  pop     r15
0x1800362ce  pop     rdi
0x1800362cf  pop     rbx
0x1800362d0  pop     rbp
0x1800362d1  retn
```
