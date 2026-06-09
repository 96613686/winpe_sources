# ISAPI_REQUEST::SendCustomError(unsigned __int64,char *,ushort)

- ea: `0x18000f5a0`
- end: `0x18000f736`
- name: `?SendCustomError@ISAPI_REQUEST@@UEAAJ_KPEADG@Z`
- size: `406`
- prototype: `int(ISAPI_REQUEST *__hidden this, unsigned __int64, char *, unsigned __int16)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x18000f5a0`
- `0x1800124c0`
- `0x180013010`

## import_xrefs

- `msvcrt!isdigit` at `0x18000f668`
- `msvcrt!isdigit` at `0x18000f668`
- `msvcrt!atoi` at `0x18000f60d`
- `msvcrt!atoi` at `0x18000f60d`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x18000f6ab`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x18000f6ab`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000f638`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000f638`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18000f5ea`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18000f5ea`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x18000f680`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x18000f680`

## pseudocode

```c
__int64 __fastcall ISAPI_REQUEST::SendCustomError(ISAPI_REQUEST *this, __int64 a2, char *a3, unsigned __int16 a4)
{
  unsigned __int16 v8; // bp
  int v9; // ebx
  __int64 v11; // r14
  __int64 (__fastcall *v12)(__int64, _QWORD, char *, _QWORD, _DWORD, _QWORD, _DWORD); // rbx
  char *Str; // rax
  int v14; // [rsp+40h] [rbp-A8h] BYREF
  _BYTE v15[56]; // [rsp+48h] [rbp-A0h] BYREF
  char v16[32]; // [rsp+80h] [rbp-68h] BYREF

  v14 = 0;
  STRA::STRA((STRA *)v15, v16, 0x20u);
  if ( a2 )
  {
    *((_QWORD *)this + 2) = a2;
    *((_DWORD *)this + 10) = 1;
  }
  v8 = atoi(a3);
  if ( (unsigned __int16)(v8 - 100) <= 0x383u )
  {
    while ( isdigit((unsigned __int8)*a3) )
      ++a3;
    if ( *a3 != 32 || (v9 = STRA::Copy((STRA *)v15, a3 + 1), v9 >= 0) )
    {
      v11 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 32LL))(*((_QWORD *)this + 3));
      v12 = *(__int64 (__fastcall **)(__int64, _QWORD, char *, _QWORD, _DWORD, _QWORD, _DWORD))(*(_QWORD *)v11 + 24LL);
      Str = STRA::QueryStr((STRA *)v15);
      v9 = v12(v11, v8, Str, a4, 0, 0, 0);
      if ( v9 >= 0 )
      {
        *((_DWORD *)this + 12) = 1;
        v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, bool, int, int *, _QWORD))(*(_QWORD *)v11 + 168LL))(
               v11,
               0,
               0,
               a2 != 0,
               1,
               &v14,
               0);
        if ( v9 >= 0 )
        {
          v9 = 0;
          goto LABEL_7;
        }
      }
    }
  }
  else
  {
    v9 = -2147024809;
  }
  if ( a2 )
    *((_DWORD *)this + 10) = 0;
LABEL_7:
  STRA::~STRA((STRA *)v15);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000f5a0  mov     r11, rsp
0x18000f5a3  push    rbx
0x18000f5a4  push    rbp
0x18000f5a5  push    rsi
0x18000f5a6  push    rdi
0x18000f5a7  push    r12
0x18000f5a9  push    r14
0x18000f5ab  push    r15
0x18000f5ad  sub     rsp, 0B0h
0x18000f5b4  mov     rax, cs:__security_cookie
0x18000f5bb  xor     rax, rsp
0x18000f5be  mov     [rsp+0E8h+var_48], rax
0x18000f5c6  mov     rbx, r8
0x18000f5c9  mov     [rsp+0E8h+var_A8], 0
0x18000f5d1  mov     rsi, rdx
0x18000f5d4  mov     rdi, rcx
0x18000f5d7  mov     r8d, 20h ; ' '
0x18000f5dd  lea     rdx, [r11-68h]
0x18000f5e1  lea     rcx, [rsp+0E8h+var_A0]
0x18000f5e6  movzx   r12d, r9w
0x18000f5ea  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x18000f5f0  xor     r15d, r15d
0x18000f5f3  test    rsi, rsi
0x18000f5f6  setnz   r15b
0x18000f5fa  test    rsi, rsi
0x18000f5fd  jz      short loc_18000F60A
0x18000f5ff  mov     [rdi+10h], rsi
0x18000f603  mov     dword ptr [rdi+28h], 1
0x18000f60a  mov     rcx, rbx; String
0x18000f60d  call    cs:__imp_atoi
0x18000f613  mov     ebp, eax
0x18000f615  lea     ecx, [rax-64h]
0x18000f618  mov     eax, 383h
0x18000f61d  cmp     cx, ax
0x18000f620  jbe     short loc_18000F665
0x18000f622  mov     ebx, 80070057h
0x18000f627  test    rsi, rsi
0x18000f62a  jz      short loc_18000F633
0x18000f62c  mov     dword ptr [rdi+28h], 0
0x18000f633  lea     rcx, [rsp+0E8h+var_A0]
0x18000f638  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18000f63e  mov     eax, ebx
0x18000f640  mov     rcx, [rsp+0E8h+var_48]
0x18000f648  xor     rcx, rsp; StackCookie
0x18000f64b  call    __security_check_cookie
0x18000f650  add     rsp, 0B0h
0x18000f657  pop     r15
0x18000f659  pop     r14
0x18000f65b  pop     r12
0x18000f65d  pop     rdi
0x18000f65e  pop     rsi
0x18000f65f  pop     rbp
0x18000f660  pop     rbx
0x18000f661  retn
0x18000f662  inc     rbx
0x18000f665  movzx   ecx, byte ptr [rbx]; C
0x18000f668  call    cs:__imp_isdigit
0x18000f66e  test    eax, eax
0x18000f670  jnz     short loc_18000F662
0x18000f672  cmp     byte ptr [rbx], 20h ; ' '
0x18000f675  jnz     short loc_18000F68C
0x18000f677  lea     rdx, [rbx+1]
0x18000f67b  lea     rcx, [rsp+0E8h+var_A0]
0x18000f680  call    cs:__imp_?Copy@STRA@@QEAAJPEBD@Z; STRA::Copy(char const *)
0x18000f686  mov     ebx, eax
0x18000f688  test    eax, eax
0x18000f68a  js      short loc_18000F627
0x18000f68c  mov     rcx, [rdi+18h]
0x18000f690  mov     rax, [rcx]
0x18000f693  mov     rax, [rax+20h]
0x18000f697  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f69c  mov     r14, rax
0x18000f69f  mov     rcx, [rax]
0x18000f6a2  mov     rbx, [rcx+18h]
0x18000f6a6  lea     rcx, [rsp+0E8h+var_A0]
0x18000f6ab  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x18000f6b1  mov     dword ptr [rsp+0E8h+var_B8], 0
0x18000f6b9  movzx   r9d, r12w
0x18000f6bd  mov     r8, rax
0x18000f6c0  mov     [rsp+0E8h+var_C0], 0
0x18000f6c9  mov     rax, rbx
0x18000f6cc  mov     [rsp+0E8h+var_C8], 0
0x18000f6d4  movzx   edx, bp
0x18000f6d7  mov     rcx, r14
0x18000f6da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f6df  mov     ebx, eax
0x18000f6e1  test    eax, eax
0x18000f6e3  js      loc_18000F627
0x18000f6e9  mov     dword ptr [rdi+30h], 1
0x18000f6f0  lea     rcx, [rsp+0E8h+var_A8]
0x18000f6f5  mov     rax, [r14]
0x18000f6f8  mov     r9d, r15d
0x18000f6fb  mov     [rsp+0E8h+var_B8], 0
0x18000f704  xor     r8d, r8d
0x18000f707  mov     [rsp+0E8h+var_C0], rcx
0x18000f70c  xor     edx, edx
0x18000f70e  mov     rcx, r14
0x18000f711  mov     [rsp+0E8h+var_C8], 1
0x18000f719  mov     rax, [rax+0A8h]
0x18000f720  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f725  mov     ebx, eax
0x18000f727  test    eax, eax
0x18000f729  js      loc_18000F627
0x18000f72f  xor     ebx, ebx
0x18000f731  jmp     loc_18000F633
```
