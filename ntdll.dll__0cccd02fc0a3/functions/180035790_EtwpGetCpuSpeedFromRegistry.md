# EtwpGetCpuSpeedFromRegistry

- ea: `0x180035790`
- end: `0x1800358d3`
- name: `EtwpGetCpuSpeedFromRegistry`
- size: `323`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180033e60`
- `0x180035a70`

## callees

- `0x180035790`
- `0x18012c830`
- `0x18015e4b0`
- `0x18015e510`
- `0x18015e5b0`
- `0x180162000`

## string_xrefs

- `0x1800357c5`: `\Registry\Machine\HARDWARE\DESCRIPTION\System\CentralProcessor\0`

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
0x180035790  push    rbp
0x180035792  push    rbx
0x180035793  push    rdi
0x180035794  push    r15
0x180035796  lea     rbp, [rsp-3Fh]
0x18003579b  sub     rsp, 0B8h
0x1800357a2  mov     rax, cs:__security_cookie
0x1800357a9  xor     rax, rsp
0x1800357ac  mov     [rbp+57h+var_30], rax
0x1800357b0  xorps   xmm0, xmm0
0x1800357b3  mov     [rbp+57h+var_A0], 0
0x1800357ba  mov     rdi, rcx
0x1800357bd  mov     [rbp+57h+Handle], 0
0x1800357c5  lea     rcx, aRegistryMachin_20; "\\Registry\\Machine\\HARDWARE\\DESCRIPT"...
0x1800357cc  xor     eax, eax
0x1800357ce  movups  [rbp+57h+var_60], xmm0
0x1800357d2  mov     [rbp+57h+var_78], rcx
0x1800357d6  movups  [rbp+57h+var_60+0Ch], xmm0
0x1800357da  mov     [rbp+57h+var_80], rax
0x1800357de  movups  [rbp+57h+var_90], xmm0
0x1800357e2  movups  [rbp+57h+var_70], xmm0
0x1800357e6  movups  [rbp+57h+var_40], xmm0
0x1800357ea  call    wcslen
0x1800357ef  add     rax, rax
0x1800357f2  mov     dword ptr [rbp+57h+var_70], 30h ; '0'
0x1800357f9  cmp     rax, 0FFFEh
0x1800357ff  mov     qword ptr [rbp+57h+var_70+8], 0
0x180035807  xorps   xmm0, xmm0
0x18003580a  mov     dword ptr [rbp+57h+var_60+8], 40h ; '@'
0x180035811  mov     r15d, 0FFFCh
0x180035817  lea     r8, [rbp+57h+var_70]
0x18003581b  cmovnb  rax, r15
0x18003581f  lea     rcx, [rbp+57h+Handle]
0x180035823  mov     word ptr [rbp+57h+var_80], ax
0x180035827  mov     ebx, 2
0x18003582c  add     ax, bx
0x18003582f  mov     edx, 20019h
0x180035834  mov     word ptr [rbp+57h+var_80+2], ax
0x180035838  lea     rax, [rbp+57h+var_80]
0x18003583c  mov     qword ptr [rbp+57h+var_60], rax
0x180035840  movdqu  [rbp+57h+var_50], xmm0
0x180035845  call    NtOpenKey
0x18003584a  test    eax, eax
0x18003584c  js      short loc_1800358B9
0x18003584e  lea     rcx, aMhz; "~MHz"
0x180035855  mov     qword ptr [rbp+57h+var_90], 0
0x18003585d  mov     qword ptr [rbp+57h+var_90+8], rcx
0x180035861  call    wcslen
0x180035866  mov     rcx, [rbp+57h+Handle]
0x18003586a  lea     r9, [rbp+57h+var_40]
0x18003586e  add     rax, rax
0x180035871  lea     rdx, [rbp+57h+var_90]
0x180035875  cmp     rax, 0FFFEh
0x18003587b  mov     r8d, ebx
0x18003587e  cmovnb  rax, r15
0x180035882  mov     word ptr [rbp+57h+var_90], ax
0x180035886  add     ax, bx
0x180035889  mov     word ptr [rbp+57h+var_90+2], ax
0x18003588d  lea     rax, [rbp+57h+var_A0]
0x180035891  mov     [rsp+0D0h+var_A8], rax
0x180035896  mov     [rsp+0D0h+var_B0], 10h
0x18003589e  call    NtQueryValueKey
0x1800358a3  mov     ebx, eax
0x1800358a5  test    eax, eax
0x1800358a7  js      short loc_1800358AE
0x1800358a9  mov     ecx, dword ptr [rbp+57h+var_40+0Ch]
0x1800358ac  mov     [rdi], ecx
0x1800358ae  mov     rcx, [rbp+57h+Handle]; Handle
0x1800358b2  call    NtClose
0x1800358b7  mov     eax, ebx
0x1800358b9  mov     rcx, [rbp+57h+var_30]
0x1800358bd  xor     rcx, rsp; StackCookie
0x1800358c0  call    __security_check_cookie
0x1800358c5  add     rsp, 0B8h
0x1800358cc  pop     r15
0x1800358ce  pop     rdi
0x1800358cf  pop     rbx
0x1800358d0  pop     rbp
0x1800358d1  retn
```
