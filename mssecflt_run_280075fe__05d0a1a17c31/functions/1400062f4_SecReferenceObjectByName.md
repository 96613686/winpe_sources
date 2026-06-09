# SecReferenceObjectByName

- ea: `0x1400062f4`
- end: `0x1400063fd`
- name: `SecReferenceObjectByName`
- size: `265`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400412c4`

## callees

- `0x1400062f4`
- `0x140011650`

## import_xrefs

- `ntoskrnl!ObOpenObjectByName` at `0x140006386`
- `ntoskrnl!ObOpenObjectByName` at `0x140006386`
- `ntoskrnl!ZwClose` at `0x1400063cd`
- `ntoskrnl!ZwClose` at `0x1400063cd`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400063b6`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400063b6`

## pseudocode

```c
__int64 __fastcall SecReferenceObjectByName(
        __int64 a1,
        int a2,
        __int64 a3,
        ACCESS_MASK a4,
        struct _OBJECT_TYPE *ObjectType,
        KPROCESSOR_MODE AccessMode,
        __int64 a7,
        PVOID *Object)
{
  __int64 v9; // r9
  NTSTATUS v10; // ebx
  HANDLE Handle; // [rsp+40h] [rbp-40h] BYREF
  _DWORD v13[2]; // [rsp+48h] [rbp-38h] BYREF
  __int64 v14; // [rsp+50h] [rbp-30h]
  __int64 v15; // [rsp+58h] [rbp-28h]
  int v16; // [rsp+60h] [rbp-20h]
  int v17; // [rsp+64h] [rbp-1Ch]
  __int128 v18; // [rsp+68h] [rbp-18h]

  v13[1] = 0;
  v17 = 0;
  Handle = 0;
  if ( !Object || !ObjectType || !a1 )
    return 3221225485LL;
  v15 = a1;
  v14 = 0;
  v9 = a3;
  LOBYTE(a3) = AccessMode;
  v16 = a2;
  v13[0] = 48;
  v18 = 0;
  v10 = ObOpenObjectByName(v13, ObjectType, a3, v9, a4, a7, &Handle);
  if ( v10 >= 0 )
  {
    _mm_lfence();
    v10 = ObReferenceObjectByHandle(Handle, a4, ObjectType, AccessMode, Object, 0);
  }
  if ( Handle )
    ZwClose(Handle);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1400062f4  push    rbp
0x1400062f6  push    rbx
0x1400062f7  push    rsi
0x1400062f8  push    rdi
0x1400062f9  push    r14
0x1400062fb  mov     rbp, rsp
0x1400062fe  sub     rsp, 80h
0x140006305  mov     rax, cs:__security_cookie
0x14000630c  xor     rax, rsp
0x14000630f  mov     [rbp+var_8], rax
0x140006313  mov     r14, [rbp+arg_38]
0x140006317  mov     esi, r9d
0x14000631a  mov     rdi, [rbp+ObjectType]
0x14000631e  xor     r9d, r9d
0x140006321  mov     rax, [rbp+arg_30]
0x140006325  mov     [rbp+var_34], r9d
0x140006329  mov     [rbp+var_1C], r9d
0x14000632d  mov     [rbp+Handle], r9
0x140006331  test    r14, r14
0x140006334  jz      loc_1400063DD
0x14000633a  test    rdi, rdi
0x14000633d  jz      loc_1400063DD
0x140006343  test    rcx, rcx
0x140006346  jz      loc_1400063DD
0x14000634c  mov     [rbp+var_28], rcx
0x140006350  xorps   xmm0, xmm0
0x140006353  lea     rcx, [rbp+Handle]
0x140006357  mov     [rbp+var_30], r9
0x14000635b  mov     [rsp+80h+var_50], rcx
0x140006360  mov     r9, r8
0x140006363  mov     r8b, [rbp+AccessMode]
0x140006367  lea     rcx, [rbp+var_38]
0x14000636b  mov     [rbp+var_20], edx
0x14000636e  mov     rdx, rdi
0x140006371  mov     [rsp+80h+HandleInformation], rax
0x140006376  mov     dword ptr [rsp+80h+Object], esi
0x14000637a  mov     [rbp+var_38], 30h ; '0'
0x140006381  movdqu  [rbp+var_18], xmm0
0x140006386  call    cs:__imp_ObOpenObjectByName
0x14000638d  nop     dword ptr [rax+rax+00h]
0x140006392  mov     ebx, eax
0x140006394  test    eax, eax
0x140006396  js      short loc_1400063C4
0x140006398  lfence
0x14000639b  mov     r9b, [rbp+AccessMode]; AccessMode
0x14000639f  mov     r8, rdi; ObjectType
0x1400063a2  mov     rcx, [rbp+Handle]; Handle
0x1400063a6  mov     edx, esi; DesiredAccess
0x1400063a8  mov     [rsp+80h+HandleInformation], 0; HandleInformation
0x1400063b1  mov     [rsp+80h+Object], r14; Object
0x1400063b6  call    cs:__imp_ObReferenceObjectByHandle
0x1400063bd  nop     dword ptr [rax+rax+00h]
0x1400063c2  mov     ebx, eax
0x1400063c4  mov     rcx, [rbp+Handle]; Handle
0x1400063c8  test    rcx, rcx
0x1400063cb  jz      short loc_1400063D9
0x1400063cd  call    cs:__imp_ZwClose
0x1400063d4  nop     dword ptr [rax+rax+00h]
0x1400063d9  mov     eax, ebx
0x1400063db  jmp     short loc_1400063E2
0x1400063dd  mov     eax, 0C000000Dh
0x1400063e2  mov     rcx, [rbp+var_8]
0x1400063e6  xor     rcx, rsp; StackCookie
0x1400063e9  call    __security_check_cookie
0x1400063ee  add     rsp, 80h
0x1400063f5  pop     r14
0x1400063f7  pop     rdi
0x1400063f8  pop     rsi
0x1400063f9  pop     rbx
0x1400063fa  pop     rbp
0x1400063fb  retn
```
