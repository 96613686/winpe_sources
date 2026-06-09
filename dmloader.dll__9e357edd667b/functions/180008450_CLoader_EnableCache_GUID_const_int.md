# CLoader::EnableCache(_GUID const &,int)

- ea: `0x180008450`
- end: `0x18000859e`
- name: `?EnableCache@CLoader@@UEAAJAEBU_GUID@@H@Z`
- size: `334`
- prototype: `__int64 __fastcall(CLoader *__hidden this, const struct _GUID *, int)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800015d0`
- `0x180008450`
- `0x1800089e4`
- `0x180009fdc`
- `0x18000a10c`
- `0x18000a1e4`

## pseudocode

```c
__int64 __fastcall CLoader::EnableCache(CLoader *this, const struct _GUID *a2, int a3)
{
  unsigned int v3; // ebp
  bool v4; // zf
  CClass **v8; // rdi
  CClass *v9; // rax
  CClass *v10; // rsi
  __int128 v11; // xmm0
  unsigned __int64 v12; // rdx
  struct CClass *v13; // rdi
  struct CClass *v15; // [rsp+20h] [rbp-E8h] BYREF
  char v16[8]; // [rsp+30h] [rbp-D8h] BYREF
  int v17; // [rsp+38h] [rbp-D0h]
  __int128 v18; // [rsp+4Ch] [rbp-BCh]

  v3 = 0;
  v4 = *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_DirectMusicAllTypes.Data1;
  v15 = 0;
  if ( v4 && *(_QWORD *)a2->Data4 == *(_QWORD *)GUID_DirectMusicAllTypes.Data4 )
  {
    v8 = (CClass **)*((_QWORD *)this + 3);
    if ( v8 )
    {
      if ( a3 )
      {
        v9 = (CClass *)*((_QWORD *)this + 3);
        do
        {
          if ( *((_DWORD *)v9 + 48) == a3 )
            v3 = 1;
          else
            *((_DWORD *)v9 + 48) = a3;
          v9 = *v8;
          v8 = (CClass **)v9;
        }
        while ( v9 );
      }
      else
      {
        v10 = (CClass *)*((_QWORD *)this + 3);
        do
        {
          CClass::ClearCache(v10);
          if ( *((_DWORD *)v10 + 48) )
            *((_DWORD *)v10 + 48) = 0;
          else
            v3 = 1;
          v10 = *v8;
          v8 = (CClass **)v10;
        }
        while ( v10 );
      }
    }
    *((_DWORD *)this + 5) = a3;
  }
  else
  {
    CDescriptor::CDescriptor((CDescriptor *)v16);
    v11 = (__int128)*a2;
    v17 = 2;
    v18 = v11;
    CLoader::GetClass(this, (struct CDescriptor *)v16, &v15, 1);
    v13 = v15;
    if ( v15 )
    {
      if ( !a3 )
        CClass::ClearCache(v15);
      if ( *((_DWORD *)v13 + 48) == a3 )
        v3 = 1;
      else
        *((_DWORD *)v13 + 48) = a3;
    }
    CDescriptor::~CDescriptor((CDescriptor *)v16, v12);
  }
  return v3;
}

```

## disassembly

```asm
0x180008450  mov     [rsp+arg_10], rbx
0x180008455  mov     [rsp+arg_18], rbp
0x18000845a  push    rsi
0x18000845b  push    rdi
0x18000845c  push    r14
0x18000845e  sub     rsp, 0F0h
0x180008465  mov     rax, cs:__security_cookie
0x18000846c  xor     rax, rsp
0x18000846f  mov     [rsp+108h+var_28], rax
0x180008477  mov     rax, [rdx]
0x18000847a  xor     ebp, ebp
0x18000847c  cmp     rax, qword ptr cs:GUID_DirectMusicAllTypes.Data1
0x180008483  mov     ebx, r8d
0x180008486  mov     rdi, rdx
0x180008489  mov     [rsp+108h+var_E8], 0
0x180008492  mov     r14, rcx
0x180008495  jnz     short loc_18000850C
0x180008497  mov     rax, [rdx+8]
0x18000849b  cmp     rax, qword ptr cs:GUID_DirectMusicAllTypes.Data4
0x1800084a2  jnz     short loc_18000850C
0x1800084a4  mov     rdi, [rcx+18h]
0x1800084a8  test    rdi, rdi
0x1800084ab  jz      short loc_180008506
0x1800084ad  test    ebx, ebx
0x1800084af  jz      short loc_1800084D6
0x1800084b1  mov     rax, rdi
0x1800084b4  cmp     [rax+0C0h], ebx
0x1800084ba  jz      short loc_1800084C4
0x1800084bc  mov     [rax+0C0h], ebx
0x1800084c2  jmp     short loc_1800084C9
0x1800084c4  mov     ebp, 1
0x1800084c9  mov     rax, [rdi]
0x1800084cc  mov     rdi, rax
0x1800084cf  test    rax, rax
0x1800084d2  jnz     short loc_1800084B4
0x1800084d4  jmp     short loc_180008506
0x1800084d6  mov     rsi, rdi
0x1800084d9  mov     rcx, rsi; this
0x1800084dc  call    ?ClearCache@CClass@@QEAAJ_N@Z; CClass::ClearCache(bool)
0x1800084e1  cmp     dword ptr [rsi+0C0h], 0
0x1800084e8  jz      short loc_1800084F6
0x1800084ea  mov     dword ptr [rsi+0C0h], 0
0x1800084f4  jmp     short loc_1800084FB
0x1800084f6  mov     ebp, 1
0x1800084fb  mov     rsi, [rdi]
0x1800084fe  mov     rdi, rsi
0x180008501  test    rsi, rsi
0x180008504  jnz     short loc_1800084D9
0x180008506  mov     [r14+14h], ebx
0x18000850a  jmp     short loc_180008574
0x18000850c  lea     rcx, [rsp+108h+var_D8]; this
0x180008511  call    ??0CDescriptor@@QEAA@XZ; CDescriptor::CDescriptor(void)
0x180008516  movups  xmm0, xmmword ptr [rdi]
0x180008519  mov     r9d, 1; int
0x18000851f  mov     [rsp+108h+var_D0], 2
0x180008527  lea     r8, [rsp+108h+var_E8]; struct CClass **
0x18000852c  mov     rcx, r14; this
0x18000852f  lea     rdx, [rsp+108h+var_D8]; struct CDescriptor *
0x180008534  movdqu  [rsp+108h+var_BC], xmm0
0x18000853a  call    ?GetClass@CLoader@@AEAAJPEAVCDescriptor@@PEAPEAVCClass@@H@Z; CLoader::GetClass(CDescriptor *,CClass * *,int)
0x18000853f  mov     rdi, [rsp+108h+var_E8]
0x180008544  test    rdi, rdi
0x180008547  jz      short loc_18000856A
0x180008549  test    ebx, ebx
0x18000854b  jnz     short loc_180008555
0x18000854d  mov     rcx, rdi; this
0x180008550  call    ?ClearCache@CClass@@QEAAJ_N@Z; CClass::ClearCache(bool)
0x180008555  cmp     [rdi+0C0h], ebx
0x18000855b  jz      short loc_180008565
0x18000855d  mov     [rdi+0C0h], ebx
0x180008563  jmp     short loc_18000856A
0x180008565  mov     ebp, 1
0x18000856a  lea     rcx, [rsp+108h+var_D8]; this
0x18000856f  call    ??1CDescriptor@@QEAA@XZ; CDescriptor::~CDescriptor(void)
0x180008574  mov     eax, ebp
0x180008576  mov     rcx, [rsp+108h+var_28]
0x18000857e  xor     rcx, rsp; StackCookie
0x180008581  call    __security_check_cookie
0x180008586  lea     r11, [rsp+108h+var_18]
0x18000858e  mov     rbx, [r11+30h]
0x180008592  mov     rbp, [r11+38h]
0x180008596  mov     rsp, r11
0x180008599  pop     r14
0x18000859b  pop     rdi
0x18000859c  pop     rsi
0x18000859d  retn
```
