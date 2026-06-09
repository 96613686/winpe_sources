# IIS_CONFIG::Update(IIS_CONFIG *)

- ea: `0x18000abfc`
- end: `0x18000ae96`
- name: `?Update@IIS_CONFIG@@QEAAJPEAV1@@Z`
- size: `666`
- prototype: `__int64 __fastcall(IIS_CONFIG *__hidden this, struct IIS_CONFIG *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x18000e510`

## callees

- `0x180001048`
- `0x180009c00`
- `0x180009cb0`
- `0x18000abfc`
- `0x18000ae9c`
- `0x18000edde`
- `0x18000ee10`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ac40`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ac40`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ae5d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ae5d`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x18000acab`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x18000acab`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000ae68`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000ae68`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000ac30`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000ac30`
- `iisutil!SAFE_snwprintf` at `0x18000acef`
- `iisutil!SAFE_snwprintf` at `0x18000acef`

## pseudocode

```c
__int64 __fastcall IIS_CONFIG::Update(IIS_CONFIG *this, struct IIS_CONFIG *a2)
{
  int v3; // r15d
  __int64 v5; // rcx
  unsigned int v6; // esi
  IIS_CONFIG_RECORD *v7; // rbp
  int v8; // r8d
  struct IIS_CONFIG_RECORD *Key; // rax
  __int64 v10; // rax
  void *v11; // r14
  __int64 v12; // rsi
  IIS_CONFIG_RECORD *i; // rbp
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 j; // r9
  unsigned int v17; // r8d
  __int64 v18; // r10
  unsigned __int16 *v19; // rdx
  unsigned __int16 v20; // ax
  unsigned __int16 v21; // cx
  __int64 v22; // rcx
  _BYTE v24[32]; // [rsp+20h] [rbp-78h] BYREF
  unsigned __int16 *v25; // [rsp+40h] [rbp-58h]

  v3 = 0;
  STRU::STRU((STRU *)v24);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 1096));
  if ( *((_QWORD *)a2 + 134) )
  {
    v5 = *((_QWORD *)this + 134);
    if ( v5 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
      *((_QWORD *)this + 134) = 0;
    }
    *((_QWORD *)this + 134) = *((_QWORD *)a2 + 134);
    *((_DWORD *)this + 270) = *((_DWORD *)a2 + 270);
    *((_QWORD *)a2 + 134) = 0;
    goto LABEL_27;
  }
  if ( !*((_QWORD *)this + 133) )
    goto LABEL_16;
  v3 = STRU::Resize((STRU *)v24, 0x400u);
  if ( v3 < 0 )
    goto LABEL_27;
  v6 = 0;
  if ( !*((_DWORD *)a2 + 264) )
  {
LABEL_12:
    v10 = *((_QWORD *)this + 133);
    if ( v10 )
    {
      v11 = (void *)(v10 - 8);
      v12 = *(_QWORD *)(v10 - 8);
      for ( i = (IIS_CONFIG_RECORD *)(v10 + 416 * v12); v12; --v12 )
      {
        i = (IIS_CONFIG_RECORD *)((char *)i - 416);
        IIS_CONFIG_RECORD::~IIS_CONFIG_RECORD(i);
      }
      operator delete(v11);
    }
LABEL_16:
    *((_QWORD *)this + 133) = *((_QWORD *)a2 + 133);
    *((_DWORD *)this + 264) = *((_DWORD *)a2 + 264);
    *((_QWORD *)a2 + 133) = 0;
    memset_0(this, 0, 0x418u);
    for ( j = 0; (unsigned int)j < *((_DWORD *)this + 264); *((_QWORD *)this + v15) = v18 )
    {
      v17 = 0;
      v18 = *((_QWORD *)this + 133) + 416LL * (unsigned int)j;
      v19 = *(unsigned __int16 **)v18;
      v20 = **(_WORD **)v18;
      if ( *((_DWORD *)this + 262) )
      {
        while ( v20 )
        {
          ++v19;
          v17 = v20 + 101 * v17;
          v20 = *v19;
        }
      }
      else
      {
        while ( v20 )
        {
          v21 = v20;
          v20 = *++v19;
          v17 = (v21 & 0xFFDF) + 101 * v17;
        }
      }
      j = (unsigned int)(j + 1);
      v14 = v17 / 0x83;
      v15 = v17 % 0x83;
      *(_QWORD *)(v18 + 8) = *((_QWORD *)this + v15);
    }
    v22 = *((_QWORD *)this + 134);
    if ( v22 )
    {
      (*(void (__fastcall **)(__int64, __int64, __int64, __int64))(*(_QWORD *)v22 + 16LL))(v22, v14, v15, j);
      *((_QWORD *)this + 134) = 0;
      *((_DWORD *)this + 270) = 0;
    }
    goto LABEL_27;
  }
  while ( 1 )
  {
    v7 = (IIS_CONFIG_RECORD *)(*((_QWORD *)a2 + 133) + 416LL * v6);
    v3 = SAFE_snwprintf((struct STRU *)v24, L"%s|%s", *((_QWORD *)v7 + 14), *((_QWORD *)v7 + 21));
    if ( v3 < 0 )
      break;
    Key = STATIC_WSTRING_HASH::FindKey(this, v25, v8);
    if ( Key )
      IIS_CONFIG_RECORD::Update(v7, Key);
    if ( ++v6 >= *((_DWORD *)a2 + 264) )
      goto LABEL_12;
  }
LABEL_27:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 1096));
  STRU::~STRU((STRU *)v24);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000abfc  mov     [rsp+arg_10], rbx
0x18000ac01  push    rbp
0x18000ac02  push    rsi
0x18000ac03  push    rdi
0x18000ac04  push    r12
0x18000ac06  push    r13
0x18000ac08  push    r14
0x18000ac0a  push    r15
0x18000ac0c  sub     rsp, 60h
0x18000ac10  mov     rax, cs:__security_cookie
0x18000ac17  xor     rax, rsp
0x18000ac1a  mov     [rsp+98h+var_40], rax
0x18000ac1f  mov     rbx, rcx
0x18000ac22  xor     r13d, r13d
0x18000ac25  lea     rcx, [rsp+98h+var_78]
0x18000ac2a  mov     r15d, r13d
0x18000ac2d  mov     rdi, rdx
0x18000ac30  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000ac36  lea     r12, [rbx+448h]
0x18000ac3d  mov     rcx, r12; lpCriticalSection
0x18000ac40  call    cs:__imp_EnterCriticalSection
0x18000ac46  cmp     [rdi+430h], r13
0x18000ac4d  jz      short loc_18000AC94
0x18000ac4f  mov     rcx, [rbx+430h]
0x18000ac56  test    rcx, rcx
0x18000ac59  jz      short loc_18000AC6E
0x18000ac5b  mov     rax, [rcx]
0x18000ac5e  mov     rax, [rax+10h]
0x18000ac62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ac67  mov     [rbx+430h], r13
0x18000ac6e  mov     rax, [rdi+430h]
0x18000ac75  mov     [rbx+430h], rax
0x18000ac7c  mov     eax, [rdi+438h]
0x18000ac82  mov     [rbx+438h], eax
0x18000ac88  mov     [rdi+430h], r13
0x18000ac8f  jmp     loc_18000AE5A
0x18000ac94  cmp     [rbx+428h], r13
0x18000ac9b  jz      loc_18000AD66
0x18000aca1  mov     edx, 400h
0x18000aca6  lea     rcx, [rsp+98h+var_78]
0x18000acab  call    cs:__imp_?Resize@STRU@@QEAAJK@Z; STRU::Resize(ulong)
0x18000acb1  mov     r15d, eax
0x18000acb4  test    eax, eax
0x18000acb6  js      loc_18000AE5A
0x18000acbc  mov     esi, r13d
0x18000acbf  cmp     [rdi+420h], r13d
0x18000acc6  jbe     short loc_18000AD27
0x18000acc8  mov     eax, esi
0x18000acca  lea     rdx, aSS_0; "%s|%s"
0x18000acd1  imul    rbp, rax, 1A0h
0x18000acd8  lea     rcx, [rsp+98h+var_78]
0x18000acdd  add     rbp, [rdi+428h]
0x18000ace4  mov     r9, [rbp+0A8h]
0x18000aceb  mov     r8, [rbp+70h]
0x18000acef  call    cs:__imp_?SAFE_snwprintf@@YAJPEAVSTRU@@PEBGZZ; SAFE_snwprintf(STRU *,ushort const *,...)
0x18000acf5  mov     r15d, eax
0x18000acf8  test    eax, eax
0x18000acfa  js      loc_18000AE5A
0x18000ad00  mov     rdx, [rsp+98h+var_58]; unsigned __int16 *
0x18000ad05  mov     rcx, rbx; this
0x18000ad08  call    ?FindKey@STATIC_WSTRING_HASH@@QEAAPEAUSTATIC_WSTRING_HASH_RECORD@@PEBGH@Z; STATIC_WSTRING_HASH::FindKey(ushort const *,int)
0x18000ad0d  test    rax, rax
0x18000ad10  jz      short loc_18000AD1D
0x18000ad12  mov     rdx, rax; struct IIS_CONFIG_RECORD *
0x18000ad15  mov     rcx, rbp; this
0x18000ad18  call    ?Update@IIS_CONFIG_RECORD@@QEAAXPEAV1@@Z; IIS_CONFIG_RECORD::Update(IIS_CONFIG_RECORD *)
0x18000ad1d  inc     esi
0x18000ad1f  cmp     esi, [rdi+420h]
0x18000ad25  jb      short loc_18000ACC8
0x18000ad27  mov     rax, [rbx+428h]
0x18000ad2e  test    rax, rax
0x18000ad31  jz      short loc_18000AD66
0x18000ad33  lea     r14, [rax-8]
0x18000ad37  mov     rsi, [r14]
0x18000ad3a  imul    rbp, rsi, 1A0h
0x18000ad41  add     rbp, rax
0x18000ad44  test    rsi, rsi
0x18000ad47  jz      short loc_18000AD5E
0x18000ad49  sub     rbp, 1A0h
0x18000ad50  mov     rcx, rbp; this
0x18000ad53  call    ??1IIS_CONFIG_RECORD@@QEAA@XZ; IIS_CONFIG_RECORD::~IIS_CONFIG_RECORD(void)
0x18000ad58  sub     rsi, 1
0x18000ad5c  jnz     short loc_18000AD49
0x18000ad5e  mov     rcx, r14; Block
0x18000ad61  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000ad66  mov     rax, [rdi+428h]
0x18000ad6d  xor     edx, edx; Val
0x18000ad6f  mov     [rbx+428h], rax
0x18000ad76  mov     r8d, 418h; Size
0x18000ad7c  mov     eax, [rdi+420h]
0x18000ad82  mov     rcx, rbx; void *
0x18000ad85  mov     [rbx+420h], eax
0x18000ad8b  mov     [rdi+428h], r13
0x18000ad92  call    memset_0
0x18000ad97  mov     r9d, r13d
0x18000ad9a  cmp     [rbx+420h], r13d
0x18000ada1  jbe     loc_18000AE34
0x18000ada7  mov     r11d, 0FA232CF3h
0x18000adad  mov     eax, r9d
0x18000adb0  mov     r8d, r13d
0x18000adb3  imul    r10, rax, 1A0h
0x18000adba  add     r10, [rbx+428h]
0x18000adc1  mov     rdx, [r10]
0x18000adc4  movzx   eax, word ptr [rdx]
0x18000adc7  cmp     [rbx+418h], r13d
0x18000adce  jz      short loc_18000AE01
0x18000add0  jmp     short loc_18000ADE3
0x18000add2  movzx   eax, ax
0x18000add5  lea     rdx, [rdx+2]
0x18000add9  imul    r8d, 65h ; 'e'
0x18000addd  add     r8d, eax
0x18000ade0  movzx   eax, word ptr [rdx]
0x18000ade3  test    ax, ax
0x18000ade6  jnz     short loc_18000ADD2
0x18000ade8  jmp     short loc_18000AE06
0x18000adea  movzx   ecx, ax
0x18000aded  lea     rdx, [rdx+2]
0x18000adf1  movzx   eax, word ptr [rdx]
0x18000adf4  and     ecx, 0FFDFh
0x18000adfa  imul    r8d, 65h ; 'e'
0x18000adfe  add     r8d, ecx
0x18000ae01  test    ax, ax
0x18000ae04  jnz     short loc_18000ADEA
0x18000ae06  mov     eax, r11d
0x18000ae09  inc     r9d
0x18000ae0c  mul     r8d
0x18000ae0f  shr     edx, 7
0x18000ae12  imul    eax, edx, 83h
0x18000ae18  sub     r8d, eax
0x18000ae1b  mov     rax, [rbx+r8*8]
0x18000ae1f  mov     [r10+8], rax
0x18000ae23  mov     [rbx+r8*8], r10
0x18000ae27  cmp     r9d, [rbx+420h]
0x18000ae2e  jb      loc_18000ADAD
0x18000ae34  mov     rcx, [rbx+430h]
0x18000ae3b  test    rcx, rcx
0x18000ae3e  jz      short loc_18000AE5A
0x18000ae40  mov     rax, [rcx]
0x18000ae43  mov     rax, [rax+10h]
0x18000ae47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae4c  mov     [rbx+430h], r13
0x18000ae53  mov     [rbx+438h], r13d
0x18000ae5a  mov     rcx, r12; lpCriticalSection
0x18000ae5d  call    cs:__imp_LeaveCriticalSection
0x18000ae63  lea     rcx, [rsp+98h+var_78]
0x18000ae68  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000ae6e  mov     eax, r15d
0x18000ae71  mov     rcx, [rsp+98h+var_40]
0x18000ae76  xor     rcx, rsp; StackCookie
0x18000ae79  call    __security_check_cookie
0x18000ae7e  mov     rbx, [rsp+98h+arg_10]
0x18000ae86  add     rsp, 60h
0x18000ae8a  pop     r15
0x18000ae8c  pop     r14
0x18000ae8e  pop     r13
0x18000ae90  pop     r12
0x18000ae92  pop     rdi
0x18000ae93  pop     rsi
0x18000ae94  pop     rbp
0x18000ae95  retn
```
