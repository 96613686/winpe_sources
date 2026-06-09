# SspipLogonUser

- ea: `0x1800076a0`
- end: `0x180007a05`
- name: `SspipLogonUser`
- size: `869`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x18001f730`

## callees

- `0x1800076a0`
- `0x18000f834`
- `0x1800108a0`
- `0x180010980`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x1800077c7`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1800077c7`
- `ntoskrnl!PsGetCurrentProcess` at `0x1800077a4`
- `ntoskrnl!PsGetCurrentProcess` at `0x1800077a4`
- `ntoskrnl!PsGetProcessId` at `0x1800077b3`
- `ntoskrnl!PsGetProcessId` at `0x1800077b3`
- `msrpc!I_RpcExceptionFilter` at `0x180011422`
- `msrpc!I_RpcExceptionFilter` at `0x180011422`

## pseudocode

```c
__int64 __fastcall SspipLogonUser(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        int a6,
        __int64 a7,
        __int64 a8,
        _QWORD *a9,
        __int64 a10,
        __int64 a11,
        _QWORD *a12,
        _OWORD *a13,
        __int64 a14)
{
  unsigned int v14; // r13d
  struct _KPROCESS *CurrentProcess; // rax
  __int64 result; // rax
  int v18; // [rsp+90h] [rbp-108h]
  __int64 v19; // [rsp+98h] [rbp-100h] BYREF
  __int64 v20; // [rsp+A0h] [rbp-F8h] BYREF
  __int64 v21; // [rsp+A8h] [rbp-F0h]
  __int64 v22; // [rsp+B0h] [rbp-E8h]
  __int64 v23; // [rsp+B8h] [rbp-E0h]
  __int64 v24; // [rsp+C0h] [rbp-D8h]
  __int64 v25; // [rsp+C8h] [rbp-D0h]
  _DWORD v26[2]; // [rsp+D0h] [rbp-C8h] BYREF
  __int64 v27; // [rsp+D8h] [rbp-C0h]
  __int64 v28; // [rsp+E0h] [rbp-B8h]
  __int64 v29; // [rsp+E8h] [rbp-B0h]
  _OWORD *v30; // [rsp+F0h] [rbp-A8h]
  _QWORD *v31; // [rsp+F8h] [rbp-A0h]
  _QWORD *v32; // [rsp+100h] [rbp-98h]
  _QWORD v33[2]; // [rsp+110h] [rbp-88h] BYREF
  __int128 v34; // [rsp+120h] [rbp-78h] BYREF
  __int128 v35; // [rsp+130h] [rbp-68h]
  __int128 v36; // [rsp+140h] [rbp-58h]

  v18 = a4;
  v14 = a3;
  v29 = a1;
  v30 = a13;
  v24 = a7;
  v25 = a8;
  v31 = a9;
  v22 = a10;
  v21 = a11;
  v32 = a12;
  v23 = a14;
  v26[1] = 0;
  v19 = 0;
  v20 = 0;
  v34 = 0;
  v35 = 0;
  v36 = 0;
  CurrentProcess = (struct _KPROCESS *)PsGetCurrentProcess(a1, a2, a3, a4);
  v33[0] = PsGetProcessId(CurrentProcess);
  v33[1] = PsGetCurrentThreadId();
  v26[0] = a6;
  v27 = a5;
  v28 = a5;
  if ( *(_QWORD *)&WPP_MAIN_CB.DeviceType )
    result = (*(__int64 (__fastcall **)(_QWORD, _QWORD *, __int64, _QWORD, int, _DWORD *, __int64, __int64, _DWORD, _QWORD, __int64, __int64 *, __int64, __int64, __int64 *, __int128 *))(*(_QWORD *)&WPP_MAIN_CB.DeviceType + 48LL))(
               0,
               v33,
               a2,
               v14,
               v18,
               v26,
               v25,
               v24,
               0,
               0,
               v23,
               &v19,
               v22,
               v21,
               &v20,
               &v34);
  else
    result = SspirLogonUser(v29, (unsigned int)v33, a2, v14, v18, (__int64)v26, v25, v24);
  if ( (int)result >= 0 )
  {
    *a9 = v19;
    *a12 = v20;
    *a13 = v34;
    a13[1] = v35;
    a13[2] = v36;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800076a0  mov     r11, rsp
0x1800076a3  push    rbx
0x1800076a4  push    rsi
0x1800076a5  push    rdi
0x1800076a6  push    r12
0x1800076a8  push    r13
0x1800076aa  push    r14
0x1800076ac  push    r15
0x1800076ae  sub     rsp, 160h
0x1800076b5  mov     rax, cs:__security_cookie
0x1800076bc  xor     rax, rsp
0x1800076bf  mov     [rsp+198h+var_48], rax
0x1800076c7  mov     [rsp+198h+var_108], r9d
0x1800076cf  mov     r13d, r8d
0x1800076d2  mov     r12, rdx
0x1800076d5  mov     [rsp+198h+var_B0], rcx
0x1800076dd  mov     rsi, [rsp+198h+arg_60]
0x1800076e5  mov     [rsp+198h+var_A8], rsi
0x1800076ed  mov     rbx, [rsp+198h+arg_20]
0x1800076f5  mov     rax, [rsp+198h+arg_30]
0x1800076fd  mov     [rsp+198h+var_D8], rax
0x180007705  mov     rax, [rsp+198h+arg_38]
0x18000770d  mov     [rsp+198h+var_D0], rax
0x180007715  mov     r14, [rsp+198h+arg_40]
0x18000771d  mov     [rsp+198h+var_A0], r14
0x180007725  mov     rax, [rsp+198h+arg_48]
0x18000772d  mov     [rsp+198h+var_E8], rax
0x180007735  mov     rax, [rsp+198h+arg_50]
0x18000773d  mov     [rsp+198h+var_F0], rax
0x180007745  mov     r15, [rsp+198h+arg_58]
0x18000774d  mov     [rsp+198h+var_98], r15
0x180007755  mov     rdi, rsi
0x180007758  mov     rax, [rsp+198h+arg_68]
0x180007760  mov     [rsp+198h+var_E0], rax
0x180007768  xorps   xmm0, xmm0
0x18000776b  movups  [rsp+198h+var_88], xmm0
0x180007773  xorps   xmm1, xmm1
0x180007776  xor     eax, eax
0x180007778  movups  [rsp+198h+var_C8], xmm1
0x180007780  mov     [r11-0B8h], rax
0x180007787  mov     [r11-100h], rax
0x18000778e  mov     [r11-0F8h], rax
0x180007795  movups  xmmword ptr [r11-78h], xmm0
0x18000779a  movups  xmmword ptr [r11-68h], xmm0
0x18000779f  movups  xmmword ptr [r11-58h], xmm0
0x1800077a4  call    cs:__imp_PsGetCurrentProcess
0x1800077ab  nop     dword ptr [rax+rax+00h]
0x1800077b0  mov     rcx, rax; Process
0x1800077b3  call    cs:__imp_PsGetProcessId
0x1800077ba  nop     dword ptr [rax+rax+00h]
0x1800077bf  mov     qword ptr [rsp+198h+var_88], rax
0x1800077c7  call    cs:__imp_PsGetCurrentThreadId
0x1800077ce  nop     dword ptr [rax+rax+00h]
0x1800077d3  mov     qword ptr [rsp+198h+var_88+8], rax
0x1800077db  mov     eax, [rsp+198h+arg_28]
0x1800077e2  mov     dword ptr [rsp+198h+var_C8], eax
0x1800077e9  mov     qword ptr [rsp+198h+var_C8+8], rbx
0x1800077f1  mov     [rsp+198h+var_B8], rbx
0x1800077f9  mov     rax, qword ptr cs:WPP_MAIN_CB.DeviceType
0x180007800  test    rax, rax
0x180007803  jz      loc_1800078B8
0x180007809  mov     rax, [rax+30h]
0x18000780d  lea     rcx, [rsp+198h+var_78]
0x180007815  mov     [rsp+198h+var_120], rcx
0x18000781a  lea     rcx, [rsp+198h+var_F8]
0x180007822  mov     [rsp+198h+var_128], rcx
0x180007827  mov     rcx, [rsp+198h+var_F0]
0x18000782f  mov     [rsp+198h+var_130], rcx
0x180007834  mov     rcx, [rsp+198h+var_E8]
0x18000783c  mov     [rsp+198h+var_138], rcx
0x180007841  lea     rcx, [rsp+198h+var_100]
0x180007849  mov     [rsp+198h+var_140], rcx
0x18000784e  mov     rcx, [rsp+198h+var_E0]
0x180007856  mov     [rsp+198h+var_148], rcx
0x18000785b  mov     [rsp+198h+var_150], 0
0x180007864  mov     [rsp+198h+var_158], 0
0x18000786c  mov     rcx, [rsp+198h+var_D8]
0x180007874  mov     [rsp+198h+var_160], rcx
0x180007879  mov     rcx, [rsp+198h+var_D0]
0x180007881  mov     [rsp+198h+var_168], rcx
0x180007886  lea     rcx, [rsp+198h+var_C8]
0x18000788e  mov     [rsp+198h+var_170], rcx
0x180007893  mov     ecx, [rsp+198h+var_108]
0x18000789a  mov     [rsp+198h+var_178], ecx
0x18000789e  mov     r9d, r13d
0x1800078a1  mov     r8, r12
0x1800078a4  lea     rdx, [rsp+198h+var_88]
0x1800078ac  xor     ecx, ecx
0x1800078ae  call    _guard_dispatch_icall
0x1800078b3  jmp     loc_18000797E
0x1800078b8  lea     rax, [rsp+198h+var_78]
0x1800078c0  mov     [rsp+198h+var_120], rax
0x1800078c5  lea     rax, [rsp+198h+var_F8]
0x1800078cd  mov     [rsp+198h+var_128], rax
0x1800078d2  mov     rcx, [rsp+198h+var_F0]
0x1800078da  mov     [rsp+198h+var_130], rcx
0x1800078df  mov     rcx, [rsp+198h+var_E8]
0x1800078e7  mov     [rsp+198h+var_138], rcx
0x1800078ec  lea     rax, [rsp+198h+var_100]
0x1800078f4  mov     [rsp+198h+var_140], rax
0x1800078f9  mov     rcx, [rsp+198h+var_E0]
0x180007901  mov     [rsp+198h+var_148], rcx
0x180007906  mov     rcx, [rsp+198h+var_D8]
0x18000790e  mov     [rsp+198h+var_160], rcx
0x180007913  mov     rcx, [rsp+198h+var_D0]
0x18000791b  mov     [rsp+198h+var_168], rcx
0x180007920  lea     rax, [rsp+198h+var_C8]
0x180007928  mov     [rsp+198h+var_170], rax
0x18000792d  mov     ecx, [rsp+198h+var_108]
0x180007934  mov     [rsp+198h+var_178], ecx
0x180007938  mov     r9d, r13d
0x18000793b  mov     r8, r12
0x18000793e  lea     rdx, [rsp+198h+var_88]
0x180007946  mov     rcx, [rsp+198h+var_B0]
0x18000794e  call    SspirLogonUser
0x180007953  mov     [rsp+198h+var_104], eax
0x18000795a  jmp     short loc_18000797E
0x18000795c  mov     [rsp+198h+var_104], eax
0x180007963  mov     rsi, [rsp+198h+var_A8]
0x18000796b  mov     r14, [rsp+198h+var_A0]
0x180007973  mov     r15, [rsp+198h+var_98]
0x18000797b  mov     rdi, rsi
0x18000797e  test    eax, eax
0x180007980  js      short loc_1800079E1
0x180007982  mov     rax, [rsp+198h+var_100]
0x18000798a  mov     [r14], rax
0x18000798d  mov     rax, [rsp+198h+var_F8]
0x180007995  mov     [r15], rax
0x180007998  mov     rax, [rsp+198h+var_78]
0x1800079a0  mov     [rsi], rax
0x1800079a3  mov     rax, [rsp+198h+var_70]
0x1800079ab  mov     [rdi+8], rax
0x1800079af  mov     rax, [rsp+198h+var_68]
0x1800079b7  mov     [rdi+10h], rax
0x1800079bb  mov     rax, [rsp+198h+var_60]
0x1800079c3  mov     [rdi+18h], rax
0x1800079c7  mov     rax, [rsp+198h+var_58]
0x1800079cf  mov     [rdi+20h], rax
0x1800079d3  mov     rax, [rsp+198h+var_50]
0x1800079db  mov     [rdi+28h], rax
0x1800079df  xor     eax, eax
0x1800079e1  mov     rcx, [rsp+198h+var_48]
0x1800079e9  xor     rcx, rsp; StackCookie
0x1800079ec  call    __security_check_cookie
0x1800079f1  add     rsp, 160h
0x1800079f8  pop     r15
0x1800079fa  pop     r14
0x1800079fc  pop     r13
0x1800079fe  pop     r12
0x180007a00  pop     rdi
0x180007a01  pop     rsi
0x180007a02  pop     rbx
0x180007a03  retn
0x180011411  push    rbp
0x180011413  sub     rsp, 90h
0x18001141a  mov     rbp, rdx
0x18001141d  mov     rcx, [rcx]
0x180011420  mov     ecx, [rcx]; ExceptionCode
0x180011422  call    cs:__imp_I_RpcExceptionFilter
0x180011429  nop     dword ptr [rax+rax+00h]
0x18001142e  nop
0x18001142f  add     rsp, 90h
0x180011436  pop     rbp
0x180011437  retn
```
