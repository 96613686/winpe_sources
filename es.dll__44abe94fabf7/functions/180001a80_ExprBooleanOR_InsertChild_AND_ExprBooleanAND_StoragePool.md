# ExprBooleanOR::InsertChild_AND(ExprBooleanAND &,StoragePool &)

- ea: `0x180001a80`
- end: `0x180001c0c`
- name: `?InsertChild_AND@ExprBooleanOR@@QEAAXAEAVExprBooleanAND@@AEAVStoragePool@@@Z`
- size: `396`
- prototype: `void __fastcall(ExprBooleanOR *__hidden this, struct ExprBooleanAND *, struct StoragePool *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180019440`

## callees

- `0x180001a80`
- `0x180001c14`
- `0x180003d54`

## import_xrefs

- `msvcrt!malloc` at `0x180001b55`
- `msvcrt!malloc` at `0x180001b55`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180001b37`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180001b37`

## string_xrefs

- `0x180001bb0`: `com\complus\src\events\queryengine\pool.cpp`
- `0x180001bee`: `com\complus\src\events\queryengine\pool.cpp`

## pseudocode

```c
void __fastcall ExprBooleanOR::InsertChild_AND(ExprBooleanOR *this, struct ExprBooleanAND *a2, struct StoragePool *a3)
{
  __int64 v3; // r9
  int v5; // edi
  unsigned __int64 v8; // rax
  __int64 v9; // rax
  struct ExprConstant *v10; // r8
  __int64 v11; // rcx
  size_t v12; // r12
  _QWORD *v13; // r15
  __int64 v14; // rbx
  void *v15; // rax
  unsigned __int64 v16; // rax
  unsigned int v17; // edx

  v3 = *((_QWORD *)a3 + 1);
  v5 = 1;
  v8 = *(_QWORD *)(v3 + 16);
  if ( v8 >= 0x18 )
  {
    *(_QWORD *)(v3 + 16) = v8 - 24;
    v9 = *(_QWORD *)(v3 + 8);
    *(_QWORD *)(v3 + 8) = v9 + 24;
    if ( v9 )
      goto LABEL_3;
  }
  v12 = *(_QWORD *)a3;
  if ( *(_QWORD *)a3 < 0x18u )
    v12 = 48;
  v13 = CoTaskMemAlloc(0x20u);
  if ( !v13 )
  {
    v13 = 0;
    v17 = 94;
LABEL_17:
    InternalError(L"com\\complus\\src\\events\\queryengine\\pool.cpp", v17, 0xC0001204, 0x10u);
    goto LABEL_12;
  }
  v14 = *((_QWORD *)a3 + 1);
  v15 = malloc(v12);
  v13[3] = v14;
  *v13 = v15;
  v13[1] = v15;
  v13[2] = v12;
  if ( !v15 )
  {
    v17 = 34;
    goto LABEL_17;
  }
LABEL_12:
  *(_QWORD *)a3 = v12;
  *((_QWORD *)a3 + 1) = v13;
  v16 = v13[2];
  if ( v16 >= 0x18 )
  {
    v13[2] = v16 - 24;
    v9 = v13[1];
    v13[1] = v9 + 24;
    if ( v9 )
    {
LABEL_3:
      *(_QWORD *)v9 = a2;
      *(_DWORD *)(v9 + 8) = 1;
      *(_QWORD *)(v9 + 16) = 0;
      goto LABEL_4;
    }
  }
  InternalError(L"com\\complus\\src\\events\\queryengine\\pool.cpp", 0x64u, 0xC0001204, 0x10u);
  v9 = 0;
LABEL_4:
  v10 = (struct ExprConstant *)*((_QWORD *)a2 + 3);
  if ( v10 )
  {
    ExprBooleanOR::InsertChild(this, (struct ExprBooleanOR::Element *)v9, v10);
  }
  else
  {
    *(_QWORD *)(v9 + 16) = *((_QWORD *)this + 1);
    v11 = *((_QWORD *)this + 1);
    if ( v11 )
      v5 = *(_DWORD *)(v11 + 8) + 1;
    *(_DWORD *)(v9 + 8) = v5;
    *((_QWORD *)this + 1) = v9;
    *((_BYTE *)this + 16) = 0;
  }
}

```

## disassembly

```asm
0x180001a80  push    rsi
0x180001a82  push    rdi
0x180001a83  sub     rsp, 28h
0x180001a87  mov     r9, [r8+8]
0x180001a8b  mov     rsi, rcx
0x180001a8e  mov     [rsp+38h+arg_8], rbp
0x180001a93  mov     edi, 1
0x180001a98  mov     [rsp+38h+arg_18], r14
0x180001a9d  mov     rbp, rdx
0x180001aa0  mov     [rsp+38h+var_18], r15
0x180001aa5  mov     r14, r8
0x180001aa8  mov     rax, [r9+10h]
0x180001aac  cmp     rax, 18h
0x180001ab0  jb      short loc_180001B1D
0x180001ab2  add     rax, 0FFFFFFFFFFFFFFE8h
0x180001ab6  mov     [r9+10h], rax
0x180001aba  mov     rax, [r9+8]
0x180001abe  lea     rcx, [rax+18h]
0x180001ac2  mov     [r9+8], rcx
0x180001ac6  test    rax, rax
0x180001ac9  jz      short loc_180001B1D
0x180001acb  mov     [rax], rbp
0x180001ace  mov     [rax+8], edi
0x180001ad1  mov     qword ptr [rax+10h], 0
0x180001ad9  mov     r8, [rbp+18h]; struct ExprConstant *
0x180001add  mov     r15, [rsp+38h+var_18]
0x180001ae2  mov     r14, [rsp+38h+arg_18]
0x180001ae7  mov     rbp, [rsp+38h+arg_8]
0x180001aec  test    r8, r8
0x180001aef  jnz     loc_180001BCF
0x180001af5  mov     rcx, [rsi+8]
0x180001af9  mov     [rax+10h], rcx
0x180001afd  mov     rcx, [rsi+8]
0x180001b01  test    rcx, rcx
0x180001b04  jz      short loc_180001B0B
0x180001b06  mov     edi, [rcx+8]
0x180001b09  inc     edi
0x180001b0b  mov     [rax+8], edi
0x180001b0e  mov     [rsi+8], rax
0x180001b12  mov     byte ptr [rsi+10h], 0
0x180001b16  add     rsp, 28h
0x180001b1a  pop     rdi
0x180001b1b  pop     rsi
0x180001b1c  retn
0x180001b1d  mov     [rsp+38h+arg_10], r12
0x180001b22  mov     eax, 30h ; '0'
0x180001b27  mov     r12, [r8]
0x180001b2a  mov     ecx, 20h ; ' '; cb
0x180001b2f  cmp     r12, 18h
0x180001b33  cmovb   r12, rax
0x180001b37  call    cs:__imp_CoTaskMemAlloc
0x180001b3d  mov     r15, rax
0x180001b40  test    rax, rax
0x180001b43  jz      loc_180001BE0
0x180001b49  mov     [rsp+38h+arg_0], rbx
0x180001b4e  mov     rcx, r12; Size
0x180001b51  mov     rbx, [r14+8]
0x180001b55  call    cs:__imp_malloc
0x180001b5b  mov     [r15+18h], rbx
0x180001b5f  mov     rbx, [rsp+38h+arg_0]
0x180001b64  mov     [r15], rax
0x180001b67  mov     [r15+8], rax
0x180001b6b  mov     [r15+10h], r12
0x180001b6f  test    rax, rax
0x180001b72  jz      loc_180001C05
0x180001b78  mov     [r14], r12
0x180001b7b  mov     r12, [rsp+38h+arg_10]
0x180001b80  mov     [r14+8], r15
0x180001b84  mov     rax, [r15+10h]
0x180001b88  cmp     rax, 18h
0x180001b8c  jb      short loc_180001BAB
0x180001b8e  add     rax, 0FFFFFFFFFFFFFFE8h
0x180001b92  mov     [r15+10h], rax
0x180001b96  mov     rax, [r15+8]
0x180001b9a  lea     rcx, [rax+18h]
0x180001b9e  mov     [r15+8], rcx
0x180001ba2  test    rax, rax
0x180001ba5  jnz     loc_180001ACB
0x180001bab  mov     edx, 64h ; 'd'; unsigned int
0x180001bb0  lea     rcx, aComComplusSrcE_19; "com\\complus\\src\\events\\queryengine"...
0x180001bb7  mov     r9d, 10h; unsigned __int16
0x180001bbd  mov     r8d, 0C0001204h; unsigned int
0x180001bc3  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x180001bc8  xor     eax, eax
0x180001bca  jmp     loc_180001AD9
0x180001bcf  mov     rdx, rax; struct ExprBooleanOR::Element *
0x180001bd2  mov     rcx, rsi; this
0x180001bd5  add     rsp, 28h
0x180001bd9  pop     rdi
0x180001bda  pop     rsi
0x180001bdb  jmp     ?InsertChild@ExprBooleanOR@@AEAAXPEAUElement@1@AEAVExprConstant@@@Z; ExprBooleanOR::InsertChild(ExprBooleanOR::Element *,ExprConstant &)
0x180001be0  xor     r15d, r15d
0x180001be3  mov     edx, 5Eh ; '^'; unsigned int
0x180001be8  mov     r9d, 10h; unsigned __int16
0x180001bee  lea     rcx, aComComplusSrcE_19; "com\\complus\\src\\events\\queryengine"...
0x180001bf5  mov     r8d, 0C0001204h; unsigned int
0x180001bfb  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x180001c00  jmp     loc_180001B78
0x180001c05  mov     edx, 22h ; '"'
0x180001c0a  jmp     short loc_180001BE8
```
