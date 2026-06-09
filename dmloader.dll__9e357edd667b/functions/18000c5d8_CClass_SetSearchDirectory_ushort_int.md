# CClass::SetSearchDirectory(ushort *,int)

- ea: `0x18000c5d8`
- end: `0x18000c704`
- name: `?SetSearchDirectory@CClass@@QEAAJPEAGH@Z`
- size: `300`
- prototype: `__int64 __fastcall(CClass *__hidden this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x180009d30`

## callees

- `0x1800015d0`
- `0x1800019a0`
- `0x180001ef0`
- `0x18000a178`
- `0x18000abec`
- `0x18000c290`
- `0x18000c5d8`
- `0x18000f990`

## pseudocode

```c
__int64 __fastcall CClass::SetSearchDirectory(CClass *this, unsigned __int16 *a2, int a3)
{
  int v6; // ebp
  _QWORD *v7; // rbx
  _QWORD *v8; // rdi
  _QWORD *v9; // rcx
  _BYTE v10[8]; // [rsp+20h] [rbp-388h] BYREF
  _BYTE Buf1[856]; // [rsp+28h] [rbp-380h] BYREF

  if ( !a2 )
    return 2147500035LL;
  v6 = CDescriptor::SetFileName((CClass *)((char *)this + 8), a2);
  if ( v6 >= 0 )
    *((_DWORD *)this + 4) |= 0x20u;
  if ( a3 )
  {
    v7 = 0;
    while ( 1 )
    {
      v8 = (_QWORD *)*((_QWORD *)this + 25);
      if ( !v8 )
        break;
      *((_QWORD *)this + 25) = *v8;
      *v8 = 0;
      if ( v8[23]
        || (memset_0(v10, 0, 0x358u),
            CDescriptor::Get((CDescriptor *)(v8 + 1), (struct _DMUS_OBJECTDESC *)v10),
            !memcmp_0(Buf1, &GUID_DefaultGMCollection, 0x10u)) )
      {
        *v8 = v7;
        v7 = v8;
      }
      else
      {
        CObject::~CObject((CObject *)v8);
        operator delete(v8);
      }
    }
    while ( v7 )
    {
      v9 = v7;
      v7 = (_QWORD *)*v7;
      *v9 = 0;
      *v9 = *((_QWORD *)this + 25);
      *((_QWORD *)this + 25) = v9;
    }
    *((_QWORD *)this + 27) = 0;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000c5d8  mov     [rsp+arg_10], rbx
0x18000c5dd  push    rbp
0x18000c5de  push    rsi
0x18000c5df  push    rdi
0x18000c5e0  sub     rsp, 390h
0x18000c5e7  mov     rax, cs:__security_cookie
0x18000c5ee  xor     rax, rsp
0x18000c5f1  mov     [rsp+3A8h+var_28], rax
0x18000c5f9  mov     ebx, r8d
0x18000c5fc  mov     rsi, rcx
0x18000c5ff  test    rdx, rdx
0x18000c602  jnz     short loc_18000C60E
0x18000c604  mov     eax, 80004003h
0x18000c609  jmp     loc_18000C6E1
0x18000c60e  add     rcx, 8; this
0x18000c612  call    ?SetFileName@CDescriptor@@QEAAJPEAG@Z; CDescriptor::SetFileName(ushort *)
0x18000c617  mov     ebp, eax
0x18000c619  test    eax, eax
0x18000c61b  js      short loc_18000C621
0x18000c61d  or      dword ptr [rsi+10h], 20h
0x18000c621  test    ebx, ebx
0x18000c623  jz      loc_18000C6DF
0x18000c629  xor     ebx, ebx
0x18000c62b  mov     rdi, [rsi+0C8h]
0x18000c632  test    rdi, rdi
0x18000c635  jz      short loc_18000C6AF
0x18000c637  mov     rax, [rdi]
0x18000c63a  mov     [rsi+0C8h], rax
0x18000c641  mov     qword ptr [rdi], 0
0x18000c648  cmp     qword ptr [rdi+0B8h], 0
0x18000c650  jnz     short loc_18000C68D
0x18000c652  xor     edx, edx; Val
0x18000c654  lea     rcx, [rsp+3A8h+var_388]; void *
0x18000c659  mov     r8d, 358h; Size
0x18000c65f  call    memset_0
0x18000c664  lea     rcx, [rdi+8]; this
0x18000c668  lea     rdx, [rsp+3A8h+var_388]; struct _DMUS_OBJECTDESC *
0x18000c66d  call    ?Get@CDescriptor@@QEAAXPEAU_DMUS_OBJECTDESC@@@Z; CDescriptor::Get(_DMUS_OBJECTDESC *)
0x18000c672  mov     r8d, 10h; Size
0x18000c678  lea     rdx, GUID_DefaultGMCollection; Buf2
0x18000c67f  lea     rcx, [rsp+3A8h+Buf1]; Buf1
0x18000c684  call    memcmp_0
0x18000c689  test    eax, eax
0x18000c68b  jnz     short loc_18000C695
0x18000c68d  mov     [rdi], rbx
0x18000c690  mov     rbx, rdi
0x18000c693  jmp     short loc_18000C62B
0x18000c695  mov     rcx, rdi; this
0x18000c698  call    ??1CObject@@QEAA@XZ; CObject::~CObject(void)
0x18000c69d  mov     edx, 0D8h; unsigned __int64
0x18000c6a2  mov     rcx, rdi; void *
0x18000c6a5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000c6aa  jmp     loc_18000C62B
0x18000c6af  test    rbx, rbx
0x18000c6b2  jz      short loc_18000C6D4
0x18000c6b4  mov     rcx, rbx
0x18000c6b7  mov     rbx, [rbx]
0x18000c6ba  mov     qword ptr [rcx], 0
0x18000c6c1  mov     rax, [rsi+0C8h]
0x18000c6c8  mov     [rcx], rax
0x18000c6cb  mov     [rsi+0C8h], rcx
0x18000c6d2  jmp     short loc_18000C6AF
0x18000c6d4  mov     qword ptr [rsi+0D8h], 0
0x18000c6df  mov     eax, ebp
0x18000c6e1  mov     rcx, [rsp+3A8h+var_28]
0x18000c6e9  xor     rcx, rsp; StackCookie
0x18000c6ec  call    __security_check_cookie
0x18000c6f1  mov     rbx, [rsp+3A8h+arg_10]
0x18000c6f9  add     rsp, 390h
0x18000c700  pop     rdi
0x18000c701  pop     rsi
0x18000c702  pop     rbp
0x18000c703  retn
```
