# FIETWLogOperationEnd

- ea: `0x140001570`
- end: `0x14000163c`
- name: `FIETWLogOperationEnd`
- size: `204`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x140001480`
- `0x140002970`
- `0x140003140`
- `0x140016b80`
- `0x140016bc0`

## callees

- `0x140001570`
- `0x140003920`
- `0x140003a00`

## import_xrefs

- `FLTMGR!FltGetActivityIdCallbackData` at `0x1400015db`
- `FLTMGR!FltGetActivityIdCallbackData` at `0x1400015db`

## pseudocode

```c
__int64 __fastcall FIETWLogOperationEnd(__int64 a1)
{
  __int64 result; // rax
  __int64 (__fastcall *v3)(_QWORD, _QWORD *, __int64, __int64, __int16, __int128 *); // rbx
  int v4; // eax
  int ActivityIdCallbackData; // eax
  __int128 *v6; // r8
  __int16 v7; // [rsp+20h] [rbp-68h]
  __int128 v8; // [rsp+40h] [rbp-48h] BYREF
  int v9; // [rsp+50h] [rbp-38h]
  __int128 v10; // [rsp+58h] [rbp-30h] BYREF
  _QWORD v11[2]; // [rsp+68h] [rbp-20h] BYREF

  result = 0;
  v8 = 0;
  v9 = 0;
  v10 = 0;
  v3 = *(__int64 (__fastcall **)(_QWORD, _QWORD *, __int64, __int64, __int16, __int128 *))(qword_140009A00 + 24);
  if ( v3 )
  {
    v4 = *(_DWORD *)(a1 + 24);
    *(_QWORD *)&v8 = a1;
    v9 = v4;
    *((_QWORD *)&v8 + 1) = *(_QWORD *)(a1 + 32);
    v11[0] = &v8;
    v11[1] = 20;
    ActivityIdCallbackData = FltGetActivityIdCallbackData(a1, &v10);
    v6 = &v10;
    if ( ActivityIdCallbackData < 0 )
      v6 = 0;
    v7 = 1100;
    return v3(*(_QWORD *)(a1 + 8), v11, 1, 0x2000000, v7, v6);
  }
  return result;
}

```

## disassembly

```asm
0x140001570  mov     r11, rsp
0x140001573  mov     [r11+10h], rbx
0x140001577  push    rdi
0x140001578  sub     rsp, 80h
0x14000157f  mov     rax, cs:__security_cookie
0x140001586  xor     rax, rsp
0x140001589  mov     [rsp+88h+var_10], rax
0x14000158e  mov     rbx, cs:qword_140009A00
0x140001595  xorps   xmm0, xmm0
0x140001598  xor     eax, eax
0x14000159a  mov     rdi, rcx
0x14000159d  movups  [rsp+88h+var_48], xmm0
0x1400015a2  mov     [rsp+88h+var_38], eax
0x1400015a6  movups  [rsp+88h+var_30], xmm0
0x1400015ab  mov     rbx, [rbx+18h]
0x1400015af  test    rbx, rbx
0x1400015b2  jz      short loc_14000161D
0x1400015b4  mov     eax, [rcx+18h]
0x1400015b7  lea     rdx, [r11-30h]
0x1400015bb  mov     [r11-48h], rcx
0x1400015bf  mov     [rsp+88h+var_38], eax
0x1400015c3  mov     rax, [rcx+20h]
0x1400015c7  mov     [r11-40h], rax
0x1400015cb  lea     rax, [r11-48h]
0x1400015cf  mov     [r11-20h], rax
0x1400015d3  mov     qword ptr [r11-18h], 14h
0x1400015db  call    cs:__imp_FltGetActivityIdCallbackData
0x1400015e2  nop     dword ptr [rax+rax+00h]
0x1400015e7  mov     rcx, [rdi+8]
0x1400015eb  lea     r8, [rsp+88h+var_30]
0x1400015f0  xor     edx, edx
0x1400015f2  mov     r9d, 2000000h
0x1400015f8  test    eax, eax
0x1400015fa  mov     rax, rbx
0x1400015fd  cmovs   r8, rdx
0x140001601  lea     rdx, [rsp+88h+var_20]
0x140001606  mov     [rsp+88h+var_60], r8
0x14000160b  mov     r8d, 1
0x140001611  mov     [rsp+88h+var_68], 44Ch
0x140001618  call    _guard_dispatch_icall
0x14000161d  mov     rcx, [rsp+88h+var_10]
0x140001622  xor     rcx, rsp; StackCookie
0x140001625  call    __security_check_cookie
0x14000162a  mov     rbx, [rsp+88h+arg_8]
0x140001632  add     rsp, 80h
0x140001639  pop     rdi
0x14000163a  retn
```
