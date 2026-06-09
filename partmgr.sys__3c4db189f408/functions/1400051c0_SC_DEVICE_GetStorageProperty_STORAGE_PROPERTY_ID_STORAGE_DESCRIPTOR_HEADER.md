# SC_DEVICE::GetStorageProperty(_STORAGE_PROPERTY_ID,_STORAGE_DESCRIPTOR_HEADER * *)

- ea: `0x1400051c0`
- end: `0x1400053cd`
- name: `?GetStorageProperty@SC_DEVICE@@QEAAJW4_STORAGE_PROPERTY_ID@@PEAPEAU_STORAGE_DESCRIPTOR_HEADER@@@Z`
- size: `525`
- prototype: `__int64 __fastcall(SC_DEVICE *__hidden this, enum _STORAGE_PROPERTY_ID, struct _STORAGE_DESCRIPTOR_HEADER **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140009880`

## callees

- `0x1400051c0`
- `0x140010f20`
- `0x140010f60`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140005324`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005376`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000538c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005324`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005376`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000538c`
- `ntoskrnl!ExAllocatePool2` at `0x140005247`
- `ntoskrnl!ExAllocatePool2` at `0x1400052bf`
- `ntoskrnl!ExAllocatePool2` at `0x140005247`
- `ntoskrnl!ExAllocatePool2` at `0x1400052bf`

## pseudocode

```c
__int64 __fastcall SC_DEVICE::GetStorageProperty(
        SC_DEVICE *this,
        enum _STORAGE_PROPERTY_ID a2,
        struct _STORAGE_DESCRIPTOR_HEADER **a3)
{
  __int64 v4; // rax
  __int64 result; // rax
  unsigned int v7; // ebp
  __int64 Pool2; // rax
  __int64 *v9; // rsi
  struct _STORAGE_DESCRIPTOR_HEADER *v10; // rbx
  int v11; // eax
  int v12; // edi
  ULONG Size; // [rsp+40h] [rbp-58h] BYREF
  int v14; // [rsp+44h] [rbp-54h] BYREF
  __int64 v15; // [rsp+48h] [rbp-50h] BYREF
  int v16; // [rsp+50h] [rbp-48h]

  v15 = 0;
  v16 = 0;
  *a3 = 0;
  v4 = *(_QWORD *)this;
  v14 = 0;
  Size = 0;
  result = (*(__int64 (__fastcall **)(SC_DEVICE *, __int64, int *, ULONG *))(v4 + 32))(this, 6, &v14, &Size);
  if ( (int)result >= 0 )
  {
    if ( v14 )
    {
      v7 = v14 + 8;
      Pool2 = ExAllocatePool2(64, (unsigned int)(v14 + 8), 1833984851);
      v9 = (__int64 *)Pool2;
      if ( !Pool2 )
        return 3221225626LL;
      (*(void (__fastcall **)(SC_DEVICE *, __int64, __int64))(*(_QWORD *)this + 40LL))(this, 6, Pool2 + 8);
    }
    else
    {
      v7 = 12;
      v9 = &v15;
    }
    *v9 = 6;
    while ( 1 )
    {
      v10 = (struct _STORAGE_DESCRIPTOR_HEADER *)ExAllocatePool2(64, Size, 1833984851);
      if ( !v10 )
      {
        v12 = -1073741670;
        goto LABEL_16;
      }
      v11 = (*(__int64 (__fastcall **)(SC_DEVICE *, __int64, __int64 *, _QWORD, struct _STORAGE_DESCRIPTOR_HEADER *, ULONG))(*(_QWORD *)this + 16LL))(
              this,
              2954240,
              v9,
              v7,
              v10,
              Size);
      v12 = v11;
      if ( ((v11 + 0x80000000) & 0x80000000) == 0 && v11 != -2147483643 )
        goto LABEL_16;
      if ( v10->Size <= Size )
        break;
      Size = v10->Size;
      ExFreePoolWithTag(v10, 0);
    }
    v10->Size = Size;
    v12 = (*(__int64 (__fastcall **)(SC_DEVICE *, __int64, struct _STORAGE_DESCRIPTOR_HEADER *))(*(_QWORD *)this + 48LL))(
            this,
            6,
            v10);
    if ( v12 >= 0 )
    {
      *a3 = v10;
      v10 = 0;
    }
LABEL_16:
    if ( v9 != &v15 )
      ExFreePoolWithTag(v9, 0);
    if ( v10 )
      ExFreePoolWithTag(v10, 0);
    return (unsigned int)v12;
  }
  return result;
}

```

## disassembly

```asm
0x1400051c0  push    r12
0x1400051c2  push    r14
0x1400051c4  push    r15
0x1400051c6  sub     rsp, 80h
0x1400051cd  mov     rax, cs:__security_cookie
0x1400051d4  xor     rax, rsp
0x1400051d7  mov     [rsp+98h+var_40], rax
0x1400051dc  xor     eax, eax
0x1400051de  lea     r9, [rsp+98h+var_58]
0x1400051e3  xor     r12d, r12d
0x1400051e6  mov     [rsp+98h+var_50], rax
0x1400051eb  mov     [rsp+98h+var_48], eax
0x1400051ef  mov     r15, r8
0x1400051f2  mov     [r8], r12
0x1400051f5  mov     edx, 6
0x1400051fa  mov     rax, [rcx]
0x1400051fd  lea     r8, [rsp+98h+var_54]
0x140005202  mov     r14, rcx
0x140005205  mov     [rsp+98h+var_54], r12d
0x14000520a  mov     [rsp+98h+var_58], r12d
0x14000520f  mov     rax, [rax+20h]
0x140005213  call    _guard_dispatch_icall
0x140005218  test    eax, eax
0x14000521a  js      loc_1400053B1
0x140005220  mov     eax, [rsp+98h+var_54]
0x140005224  mov     [rsp+98h+var_20], rbp
0x140005229  mov     [rsp+98h+var_28], rsi
0x14000522e  mov     [rsp+98h+var_30], rdi
0x140005233  test    eax, eax
0x140005235  jz      short loc_14000527F
0x140005237  lea     ebp, [rax+8]
0x14000523a  mov     ecx, 40h ; '@'
0x14000523f  mov     edx, ebp
0x140005241  mov     r8d, 6D506353h
0x140005247  call    cs:__imp_ExAllocatePool2
0x14000524e  nop     dword ptr [rax+rax+00h]
0x140005253  mov     rsi, rax
0x140005256  test    rax, rax
0x140005259  jnz     short loc_140005265
0x14000525b  mov     eax, 0C000009Ah
0x140005260  jmp     loc_1400053A2
0x140005265  mov     rax, [r14]
0x140005268  lea     r8, [rsi+8]
0x14000526c  mov     edx, 6
0x140005271  mov     rcx, r14
0x140005274  mov     rax, [rax+28h]
0x140005278  call    _guard_dispatch_icall
0x14000527d  jmp     short loc_140005289
0x14000527f  mov     ebp, 0Ch
0x140005284  lea     rsi, [rsp+98h+var_50]
0x140005289  mov     [rsp+98h+arg_8], rbx
0x140005291  mov     [rsp+98h+var_38], r13
0x140005296  mov     r13d, 80000000h
0x14000529c  mov     qword ptr [rsi], 6
0x1400052a3  nop     dword ptr [rax+00h]
0x1400052a7  nop     word ptr [rax+rax+00000000h]
0x1400052b0  mov     edx, [rsp+98h+var_58]
0x1400052b4  mov     ecx, 40h ; '@'
0x1400052b9  mov     r8d, 6D506353h
0x1400052bf  call    cs:__imp_ExAllocatePool2
0x1400052c6  nop     dword ptr [rax+rax+00h]
0x1400052cb  mov     rbx, rax
0x1400052ce  test    rax, rax
0x1400052d1  jz      loc_14000535D
0x1400052d7  mov     ecx, [rsp+98h+var_58]
0x1400052db  mov     r9d, ebp
0x1400052de  mov     rax, [r14]
0x1400052e1  mov     r8, rsi
0x1400052e4  mov     [rsp+98h+var_70], ecx
0x1400052e8  mov     edx, 2D1400h
0x1400052ed  mov     rcx, r14
0x1400052f0  mov     [rsp+98h+var_78], rbx
0x1400052f5  mov     rax, [rax+10h]
0x1400052f9  call    _guard_dispatch_icall
0x1400052fe  mov     edi, eax
0x140005300  lea     ecx, [rax+r13]
0x140005304  test    r13d, ecx
0x140005307  jnz     short loc_140005310
0x140005309  cmp     eax, 80000005h
0x14000530e  jnz     short loc_140005362
0x140005310  mov     eax, [rbx+4]
0x140005313  mov     ecx, [rsp+98h+var_58]
0x140005317  cmp     eax, ecx
0x140005319  jbe     short loc_140005335
0x14000531b  xor     edx, edx; Tag
0x14000531d  mov     [rsp+98h+var_58], eax
0x140005321  mov     rcx, rbx; P
0x140005324  call    cs:__imp_ExFreePoolWithTag
0x14000532b  nop     dword ptr [rax+rax+00h]
0x140005330  jmp     loc_1400052B0
0x140005335  mov     [rbx+4], ecx
0x140005338  mov     r8, rbx
0x14000533b  mov     rax, [r14]
0x14000533e  mov     edx, 6
0x140005343  mov     rcx, r14
0x140005346  mov     rax, [rax+30h]
0x14000534a  call    _guard_dispatch_icall
0x14000534f  mov     edi, eax
0x140005351  test    eax, eax
0x140005353  js      short loc_140005362
0x140005355  mov     [r15], rbx
0x140005358  mov     rbx, r12
0x14000535b  jmp     short loc_140005362
0x14000535d  mov     edi, 0C000009Ah
0x140005362  mov     r13, [rsp+98h+var_38]
0x140005367  lea     rax, [rsp+98h+var_50]
0x14000536c  cmp     rsi, rax
0x14000536f  jz      short loc_140005382
0x140005371  xor     edx, edx; Tag
0x140005373  mov     rcx, rsi; P
0x140005376  call    cs:__imp_ExFreePoolWithTag
0x14000537d  nop     dword ptr [rax+rax+00h]
0x140005382  test    rbx, rbx
0x140005385  jz      short loc_140005398
0x140005387  xor     edx, edx; Tag
0x140005389  mov     rcx, rbx; P
0x14000538c  call    cs:__imp_ExFreePoolWithTag
0x140005393  nop     dword ptr [rax+rax+00h]
0x140005398  mov     rbx, [rsp+98h+arg_8]
0x1400053a0  mov     eax, edi
0x1400053a2  mov     rbp, [rsp+98h+var_20]
0x1400053a7  mov     rsi, [rsp+98h+var_28]
0x1400053ac  mov     rdi, [rsp+98h+var_30]
0x1400053b1  mov     rcx, [rsp+98h+var_40]
0x1400053b6  xor     rcx, rsp; StackCookie
0x1400053b9  call    __security_check_cookie
0x1400053be  add     rsp, 80h
0x1400053c5  pop     r15
0x1400053c7  pop     r14
0x1400053c9  pop     r12
0x1400053cb  retn
```
