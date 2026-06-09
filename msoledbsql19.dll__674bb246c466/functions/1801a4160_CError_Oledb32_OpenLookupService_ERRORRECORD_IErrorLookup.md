# CError_Oledb32::OpenLookupService(__ERRORRECORD *,IErrorLookup * *)

- ea: `0x1801a4160`
- end: `0x1801a4380`
- name: `?OpenLookupService@CError_Oledb32@@QEAAJPEAU__ERRORRECORD@@PEAPEAUIErrorLookup@@@Z`
- size: `544`
- prototype: `__int64 __fastcall(CError_Oledb32 *__hidden this, struct __ERRORRECORD *, struct IErrorLookup **)`
- caller_count: `4`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x1801a5490`
- `0x1801a59f0`
- `0x1801a5c70`
- `0x1801a5f30`

## callees

- `0x180003030`
- `0x180003d80`
- `0x1801a4160`
- `0x1801a65e1`
- `0x1801a65f0`
- `0x1801ad6a0`

## import_xrefs

- `ole32!CoCreateInstance` at `0x1801a42fd`
- `ole32!CoCreateInstance` at `0x1801a42fd`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1801a4296`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1801a4296`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1801a42a2`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1801a42a2`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CError_Oledb32::OpenLookupService(
        CError_Oledb32 *this,
        struct __ERRORRECORD *a2,
        struct IErrorLookup **a3)
{
  unsigned int Instance; // r14d
  struct IErrorLookup *v7; // rsi
  __int64 v8; // rcx
  __int64 v9; // rbx
  unsigned int v10; // edi
  size_t *v11; // rcx
  size_t v12; // r8
  __int64 v13; // rdx
  const void *v14; // rdx
  LPVOID *ppv; // rax
  _BYTE v18[16]; // [rsp+40h] [rbp-79h] BYREF
  __int128 v19; // [rsp+50h] [rbp-69h]
  __int128 v20; // [rsp+A0h] [rbp-19h]
  struct IErrorLookup *v21; // [rsp+B0h] [rbp-9h]
  __int64 v22; // [rsp+C0h] [rbp+7h]
  __int64 v23; // [rsp+C8h] [rbp+Fh]

  Instance = 0;
  v22 = 0;
  v23 = 0;
  v7 = 0;
  v19 = 0;
  v20 = 0;
  v21 = 0;
  if ( *((_OWORD *)a2 + 6) == 0 )
  {
    if ( (bidGblFlags & 2) != 0 )
      Instance = bidTraceHR(off_180262718[0], 374793, 2147500037LL);
    else
      Instance = -2147467259;
  }
  else
  {
    v8 = *((_QWORD *)a2 + 14);
    if ( v8 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 8LL))(v8);
      *a3 = (struct IErrorLookup *)*((_QWORD *)a2 + 14);
    }
    else
    {
      v9 = 0;
      v22 = 0;
      if ( this != (CError_Oledb32 *)-64LL )
      {
        v9 = *((_QWORD *)this + 8);
        v22 = v9;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)(v9 + 32) + 8LL))(v9 + 32);
      }
      v10 = 0;
      if ( *((_DWORD *)this + 10) )
      {
        while ( 1 )
        {
          v11 = (size_t *)*((_QWORD *)this + 6);
          v12 = *v11;
          v13 = 0;
          if ( v10 < v11[1] )
            v13 = v10;
          v14 = (const void *)(v11[4] + v12 * v13);
          if ( v12 )
          {
            if ( v14 )
            {
              memcpy_0(v18, v14, v12);
            }
            else
            {
              memset_0(v18, 0, v12);
              *_errno() = 22;
              _invalid_parameter_noinfo();
            }
            v7 = v21;
          }
          if ( v20 == *((_OWORD *)a2 + 6) && (_DWORD)v19 == *((_DWORD *)a2 + 4) && v7 )
            break;
          if ( ++v10 >= *((_DWORD *)this + 10) )
            goto LABEL_21;
        }
        ((void (__fastcall *)(struct IErrorLookup *, const void *))v7->lpVtbl->AddRef)(v7, v14);
        ppv = (LPVOID *)a3;
        *a3 = v7;
      }
      else
      {
LABEL_21:
        ppv = (LPVOID *)a3;
      }
      if ( v10 >= *((_DWORD *)this + 10) )
        Instance = CoCreateInstance((const IID *const)a2 + 6, 0, 1u, &IID_IErrorLookup, ppv);
      if ( v9 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)(v9 + 32) + 24LL))(v9 + 32);
    }
  }
  if ( (bidGblFlags & 2) != 0 )
    return bidTraceHR(off_180262718[0], 410633, Instance);
  else
    return Instance;
}

```

## disassembly

```asm
0x1801a4160  mov     [rsp-8+arg_18], rbx
0x1801a4165  push    rbp
0x1801a4166  push    rsi
0x1801a4167  push    rdi
0x1801a4168  push    r12
0x1801a416a  push    r13
0x1801a416c  push    r14
0x1801a416e  push    r15
0x1801a4170  lea     rbp, [rsp-27h]
0x1801a4175  sub     rsp, 0E0h
0x1801a417c  mov     rax, cs:__security_cookie
0x1801a4183  xor     rax, rsp
0x1801a4186  mov     [rbp+57h+var_40], rax
0x1801a418a  mov     rbx, r8
0x1801a418d  mov     [rsp+110h+var_E0], rbx
0x1801a4192  mov     r12, rdx
0x1801a4195  mov     r13, rcx
0x1801a4198  xor     r14d, r14d
0x1801a419b  mov     [rbp+57h+var_50], r14
0x1801a419f  mov     [rbp+57h+var_48], r14
0x1801a41a3  xorps   xmm0, xmm0
0x1801a41a6  xor     esi, esi
0x1801a41a8  movups  [rbp+57h+var_C0], xmm0
0x1801a41ac  movups  [rbp+57h+var_70], xmm0
0x1801a41b0  mov     [rbp+57h+var_60], rsi
0x1801a41b4  mov     rax, [rdx+60h]
0x1801a41b8  cmp     rax, r14
0x1801a41bb  jnz     short loc_1801A41F9
0x1801a41bd  mov     rax, [rdx+68h]
0x1801a41c1  cmp     rax, r14
0x1801a41c4  jnz     short loc_1801A41F9
0x1801a41c6  test    byte ptr cs:_bidGblFlags, 2
0x1801a41cd  jz      short loc_1801A41EE
0x1801a41cf  mov     edx, 5B809h
0x1801a41d4  mov     r8d, 80004005h
0x1801a41da  mov     rcx, cs:off_180262718; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x1801a41e1  call    _bidTraceHR
0x1801a41e6  mov     r14d, eax
0x1801a41e9  jmp     loc_1801A431D
0x1801a41ee  mov     r14d, 80004005h
0x1801a41f4  jmp     loc_1801A431D
0x1801a41f9  mov     rcx, [rdx+70h]
0x1801a41fd  test    rcx, rcx
0x1801a4200  jz      short loc_1801A421C
0x1801a4202  mov     rax, [rcx]
0x1801a4205  mov     rax, [rax+8]
0x1801a4209  call    cs:__guard_dispatch_icall_fptr
0x1801a420f  mov     rax, [r12+70h]
0x1801a4214  mov     [rbx], rax
0x1801a4217  jmp     loc_1801A431D
0x1801a421c  lea     rax, [r13+40h]
0x1801a4220  mov     rbx, r14
0x1801a4223  mov     [rbp+57h+var_50], rbx
0x1801a4227  test    rax, rax
0x1801a422a  jz      short loc_1801A4245
0x1801a422c  mov     rbx, [rax]
0x1801a422f  mov     [rbp+57h+var_50], rbx
0x1801a4233  lea     rcx, [rbx+20h]
0x1801a4237  mov     rax, [rcx]
0x1801a423a  mov     rax, [rax+8]
0x1801a423e  call    cs:__guard_dispatch_icall_fptr
0x1801a4244  nop
0x1801a4245  mov     edi, r14d
0x1801a4248  cmp     [r13+28h], r14d
0x1801a424c  jbe     loc_1801A42D9
0x1801a4252  nop     dword ptr [rax+00h]
0x1801a4256  nop     word ptr [rax+rax+00000000h]
0x1801a4260  mov     eax, edi
0x1801a4262  mov     rcx, [r13+30h]
0x1801a4266  mov     r8, [rcx]; Size
0x1801a4269  mov     rdx, r14
0x1801a426c  cmp     rax, [rcx+8]
0x1801a4270  cmovb   rdx, rax
0x1801a4274  imul    rdx, r8
0x1801a4278  add     rdx, [rcx+20h]; Src
0x1801a427c  test    r8, r8
0x1801a427f  jz      short loc_1801A42AC
0x1801a4281  lea     rcx, [rbp+57h+var_D0]; void *
0x1801a4285  test    rdx, rdx
0x1801a4288  jz      short loc_1801A4291
0x1801a428a  call    memcpy_0
0x1801a428f  jmp     short loc_1801A42A8
0x1801a4291  call    memset_0
0x1801a4296  call    cs:__imp__errno
0x1801a429c  mov     dword ptr [rax], 16h
0x1801a42a2  call    cs:__imp__invalid_parameter_noinfo
0x1801a42a8  mov     rsi, [rbp+57h+var_60]
0x1801a42ac  mov     rax, qword ptr [rbp+57h+var_70]
0x1801a42b0  cmp     rax, [r12+60h]
0x1801a42b5  jnz     short loc_1801A42D1
0x1801a42b7  mov     rax, qword ptr [rbp+57h+var_70+8]
0x1801a42bb  cmp     rax, [r12+68h]
0x1801a42c0  jnz     short loc_1801A42D1
0x1801a42c2  mov     eax, [r12+10h]
0x1801a42c7  cmp     dword ptr [rbp+57h+var_C0], eax
0x1801a42ca  jnz     short loc_1801A42D1
0x1801a42cc  test    rsi, rsi
0x1801a42cf  jnz     short loc_1801A433C
0x1801a42d1  inc     edi
0x1801a42d3  cmp     edi, [r13+28h]
0x1801a42d7  jb      short loc_1801A4260
0x1801a42d9  mov     rax, [rsp+110h+var_E0]
0x1801a42de  cmp     edi, [r13+28h]
0x1801a42e2  jb      short loc_1801A4306
0x1801a42e4  mov     [rsp+110h+ppv], rax; ppv
0x1801a42e9  lea     r9, IID_IErrorLookup; riid
0x1801a42f0  xor     edx, edx; pUnkOuter
0x1801a42f2  mov     r8d, 1; dwClsContext
0x1801a42f8  lea     rcx, [r12+60h]; rclsid
0x1801a42fd  call    cs:__imp_CoCreateInstance
0x1801a4303  mov     r14d, eax
0x1801a4306  test    rbx, rbx
0x1801a4309  jz      short loc_1801A431D
0x1801a430b  lea     rcx, [rbx+20h]
0x1801a430f  mov     rax, [rcx]
0x1801a4312  mov     rax, [rax+18h]
0x1801a4316  call    cs:__guard_dispatch_icall_fptr
0x1801a431c  nop
0x1801a431d  test    byte ptr cs:_bidGblFlags, 2
0x1801a4324  jz      short loc_1801A4356
0x1801a4326  mov     r8d, r14d
0x1801a4329  mov     edx, 64409h
0x1801a432e  mov     rcx, cs:off_180262718; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x1801a4335  call    _bidTraceHR
0x1801a433a  jmp     short loc_1801A4359
0x1801a433c  mov     rax, [rsi]
0x1801a433f  mov     rcx, rsi
0x1801a4342  mov     rax, [rax+8]
0x1801a4346  call    cs:__guard_dispatch_icall_fptr
0x1801a434c  mov     rax, [rsp+110h+var_E0]
0x1801a4351  mov     [rax], rsi
0x1801a4354  jmp     short loc_1801A42DE
0x1801a4356  mov     eax, r14d
0x1801a4359  mov     rcx, [rbp+57h+var_40]
0x1801a435d  xor     rcx, rsp; StackCookie
0x1801a4360  call    __security_check_cookie
0x1801a4365  mov     rbx, [rsp+110h+arg_18]
0x1801a436d  add     rsp, 0E0h
0x1801a4374  pop     r15
0x1801a4376  pop     r14
0x1801a4378  pop     r13
0x1801a437a  pop     r12
0x1801a437c  pop     rdi
0x1801a437d  pop     rsi
0x1801a437e  pop     rbp
0x1801a437f  retn
```
