# CCompRC::GetLibrary(ushort const *,HINSTANCE__ * *)

- ea: `0x18003eff4`
- end: `0x18003f1d4`
- name: `?GetLibrary@CCompRC@@AEAAJPEBGPEAPEAUHINSTANCE__@@@Z`
- size: `480`
- prototype: `__int64 __fastcall(CCompRC *__hidden this, const unsigned __int16 *, HINSTANCE *)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002a3b8`
- `0x18003f93c`

## callees

- `0x180039310`
- `0x180039418`
- `0x18003ed54`
- `0x18003eff4`
- `0x18003f35c`
- `0x18003f38c`
- `0x18003fa1c`
- `0x18003fa88`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x18003f0d5`
- `KERNEL32!FreeLibrary` at `0x18003f1c9`
- `KERNEL32!FreeLibrary` at `0x18003f0d5`
- `KERNEL32!FreeLibrary` at `0x18003f1c9`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CCompRC::GetLibrary(CCompRC *this, const unsigned __int16 *a2, HINSTANCE *a3)
{
  HMODULE v5; // rsi
  int v6; // r14d
  int v7; // ebx
  __int64 result; // rax
  void *v9; // r12
  int v10; // r13d
  HMODULE v11; // r9
  void *v12; // rbx
  int v13; // r12d
  void *v14; // r12
  int v15; // r13d
  int v16; // [rsp+70h] [rbp+40h]
  int v17; // [rsp+70h] [rbp+40h]
  HMODULE hLibModule; // [rsp+88h] [rbp+58h] BYREF

  hLibModule = 0;
  v5 = (HMODULE)*((_QWORD *)this + 22);
  v6 = 1;
  if ( v5 )
  {
    if ( !a2 || (unsigned int)CCulturedHInstance::HasID(this, a2) )
    {
LABEL_4:
      v7 = 0;
LABEL_5:
      *a3 = v5;
      return (unsigned int)v7;
    }
  }
  else
  {
    result = CCompRC::LoadLibrary(this, &hLibModule);
    v7 = result;
    if ( (int)result < 0 )
      return result;
    v9 = (void *)*((_QWORD *)this + 25);
    if ( v9 )
    {
      ClrEnterCriticalSection(v9);
      v10 = 1;
      v16 = 1;
    }
    else
    {
      v10 = 0;
      v16 = 0;
    }
    if ( *((_QWORD *)this + 22) )
    {
      v5 = 0;
      if ( (unsigned int)CCulturedHInstance::HasID(this, a2) )
        v5 = v11;
      FreeLibrary(hLibModule);
      v10 = v16;
    }
    else
    {
      v5 = hLibModule;
      CCulturedHInstance::Set(this, a2, hLibModule);
    }
    if ( v10 )
      ClrLeaveCriticalSection(v9);
    if ( v5 )
      goto LABEL_5;
  }
  v12 = (void *)*((_QWORD *)this + 25);
  v13 = 0;
  if ( v12 )
  {
    ClrEnterCriticalSection(*((void **)this + 25));
    v13 = 1;
  }
  v5 = CCompRC::LookupNode(this, a2);
  if ( v13 )
    ClrLeaveCriticalSection(v12);
  if ( v5 )
    goto LABEL_4;
  result = CCompRC::LoadLibrary(this, &hLibModule);
  v7 = result;
  if ( (int)result >= 0 )
  {
    v14 = (void *)*((_QWORD *)this + 25);
    if ( v14 )
    {
      ClrEnterCriticalSection(v14);
      v15 = 1;
      v17 = 1;
    }
    else
    {
      v15 = 0;
      v17 = 0;
    }
    v5 = CCompRC::LookupNode(this, a2);
    if ( v5 )
    {
      v15 = v17;
    }
    else
    {
      v5 = hLibModule;
      v7 = CCompRC::AddMapNode(this, a2, hLibModule);
      v6 = 0;
    }
    if ( v15 )
      ClrLeaveCriticalSection(v14);
    if ( v6 || v7 < 0 )
      FreeLibrary(hLibModule);
    goto LABEL_5;
  }
  return result;
}

```

## disassembly

```asm
0x18003eff4  mov     [rsp-38h+arg_8], rbx
0x18003eff9  mov     [rsp-38h+arg_10], r8
0x18003effe  push    rbp
0x18003efff  push    rsi
0x18003f000  push    rdi
0x18003f001  push    r12
0x18003f003  push    r13
0x18003f005  push    r14
0x18003f007  push    r15
0x18003f009  mov     rbp, rsp
0x18003f00c  sub     rsp, 30h
0x18003f010  mov     r15, rdx
0x18003f013  mov     rdi, rcx
0x18003f016  mov     [rbp+hLibModule], 0
0x18003f01e  mov     rsi, [rcx+0B0h]
0x18003f025  mov     r14d, 1
0x18003f02b  test    rsi, rsi
0x18003f02e  jz      short loc_18003F062
0x18003f030  test    rdx, rdx
0x18003f033  jz      short loc_18003F042
0x18003f035  call    ?HasID@CCulturedHInstance@@QEAAHPEBG@Z; CCulturedHInstance::HasID(ushort const *)
0x18003f03a  test    eax, eax
0x18003f03c  jz      loc_18003F0F6
0x18003f042  xor     ebx, ebx
0x18003f044  mov     rax, [rbp+arg_10]
0x18003f048  mov     [rax], rsi
0x18003f04b  mov     eax, ebx
0x18003f04d  mov     rbx, [rsp+30h+arg_8]
0x18003f052  add     rsp, 30h
0x18003f056  pop     r15
0x18003f058  pop     r14
0x18003f05a  pop     r13
0x18003f05c  pop     r12
0x18003f05e  pop     rdi
0x18003f05f  pop     rsi
0x18003f060  pop     rbp
0x18003f061  retn
0x18003f062  lea     rdx, [rbp+hLibModule]; HINSTANCE *
0x18003f066  call    ?LoadLibrary@CCompRC@@AEAAJPEAPEAUHINSTANCE__@@@Z; CCompRC::LoadLibrary(HINSTANCE__ * *)
0x18003f06b  mov     ebx, eax
0x18003f06d  test    eax, eax
0x18003f06f  js      short loc_18003F04D
0x18003f071  mov     r12, [rdi+0C8h]
0x18003f078  mov     [rbp+var_10], r12
0x18003f07c  mov     [rbp+var_8], 0
0x18003f083  test    r12, r12
0x18003f086  jz      short loc_18003F09D
0x18003f088  mov     rcx, r12; void *
0x18003f08b  call    ?ClrEnterCriticalSection@@YAXPEAX@Z; ClrEnterCriticalSection(void *)
0x18003f090  mov     [rbp+var_8], r14d
0x18003f094  mov     r13d, r14d
0x18003f097  mov     [rbp+arg_0], r14d
0x18003f09b  jmp     short loc_18003F0A4
0x18003f09d  xor     r13d, r13d
0x18003f0a0  mov     [rbp+arg_0], r13d
0x18003f0a4  mov     r9, [rdi+0B0h]
0x18003f0ab  mov     rdx, r15; unsigned __int16 *
0x18003f0ae  mov     rcx, rdi; this
0x18003f0b1  test    r9, r9
0x18003f0b4  jnz     short loc_18003F0C4
0x18003f0b6  mov     rsi, [rbp+hLibModule]
0x18003f0ba  mov     r8, rsi; HINSTANCE
0x18003f0bd  call    ?Set@CCulturedHInstance@@QEAAXPEBGPEAUHINSTANCE__@@@Z; CCulturedHInstance::Set(ushort const *,HINSTANCE__ *)
0x18003f0c2  jmp     short loc_18003F0DF
0x18003f0c4  xor     esi, esi
0x18003f0c6  call    ?HasID@CCulturedHInstance@@QEAAHPEBG@Z; CCulturedHInstance::HasID(ushort const *)
0x18003f0cb  test    eax, eax
0x18003f0cd  cmovnz  rsi, r9
0x18003f0d1  mov     rcx, [rbp+hLibModule]; hLibModule
0x18003f0d5  call    cs:__imp_FreeLibrary
0x18003f0db  mov     r13d, [rbp+arg_0]
0x18003f0df  test    r13d, r13d
0x18003f0e2  jz      short loc_18003F0ED
0x18003f0e4  mov     rcx, r12; void *
0x18003f0e7  call    ?ClrLeaveCriticalSection@@YAXPEAX@Z; ClrLeaveCriticalSection(void *)
0x18003f0ec  nop
0x18003f0ed  test    rsi, rsi
0x18003f0f0  jnz     loc_18003F044
0x18003f0f6  mov     rbx, [rdi+0C8h]
0x18003f0fd  xor     r12d, r12d
0x18003f100  test    rbx, rbx
0x18003f103  jz      short loc_18003F110
0x18003f105  mov     rcx, rbx; void *
0x18003f108  call    ?ClrEnterCriticalSection@@YAXPEAX@Z; ClrEnterCriticalSection(void *)
0x18003f10d  mov     r12d, r14d
0x18003f110  mov     rdx, r15; unsigned __int16 *
0x18003f113  mov     rcx, rdi; this
0x18003f116  call    ?LookupNode@CCompRC@@AEAAPEAUHINSTANCE__@@PEBG@Z; CCompRC::LookupNode(ushort const *)
0x18003f11b  mov     rsi, rax
0x18003f11e  test    r12d, r12d
0x18003f121  jz      short loc_18003F12C
0x18003f123  mov     rcx, rbx; void *
0x18003f126  call    ?ClrLeaveCriticalSection@@YAXPEAX@Z; ClrLeaveCriticalSection(void *)
0x18003f12b  nop
0x18003f12c  test    rsi, rsi
0x18003f12f  jnz     loc_18003F042
0x18003f135  lea     rdx, [rbp+hLibModule]; HINSTANCE *
0x18003f139  mov     rcx, rdi; this
0x18003f13c  call    ?LoadLibrary@CCompRC@@AEAAJPEAPEAUHINSTANCE__@@@Z; CCompRC::LoadLibrary(HINSTANCE__ * *)
0x18003f141  mov     ebx, eax
0x18003f143  test    eax, eax
0x18003f145  js      loc_18003F04D
0x18003f14b  mov     r12, [rdi+0C8h]
0x18003f152  mov     [rbp+var_10], r12
0x18003f156  mov     [rbp+var_8], esi
0x18003f159  test    r12, r12
0x18003f15c  jz      short loc_18003F173
0x18003f15e  mov     rcx, r12; void *
0x18003f161  call    ?ClrEnterCriticalSection@@YAXPEAX@Z; ClrEnterCriticalSection(void *)
0x18003f166  mov     [rbp+var_8], r14d
0x18003f16a  mov     r13d, r14d
0x18003f16d  mov     [rbp+arg_0], r14d
0x18003f171  jmp     short loc_18003F17A
0x18003f173  xor     r13d, r13d
0x18003f176  mov     [rbp+arg_0], r13d
0x18003f17a  mov     rdx, r15; unsigned __int16 *
0x18003f17d  mov     rcx, rdi; this
0x18003f180  call    ?LookupNode@CCompRC@@AEAAPEAUHINSTANCE__@@PEBG@Z; CCompRC::LookupNode(ushort const *)
0x18003f185  mov     rsi, rax
0x18003f188  test    rax, rax
0x18003f18b  jnz     short loc_18003F1A6
0x18003f18d  mov     rsi, [rbp+hLibModule]
0x18003f191  mov     r8, rsi; HINSTANCE
0x18003f194  mov     rdx, r15; unsigned __int16 *
0x18003f197  mov     rcx, rdi; this
0x18003f19a  call    ?AddMapNode@CCompRC@@AEAAJPEBGPEAUHINSTANCE__@@@Z; CCompRC::AddMapNode(ushort const *,HINSTANCE__ *)
0x18003f19f  mov     ebx, eax
0x18003f1a1  xor     r14d, r14d
0x18003f1a4  jmp     short loc_18003F1AA
0x18003f1a6  mov     r13d, [rbp+arg_0]
0x18003f1aa  test    r13d, r13d
0x18003f1ad  jz      short loc_18003F1B8
0x18003f1af  mov     rcx, r12; void *
0x18003f1b2  call    ?ClrLeaveCriticalSection@@YAXPEAX@Z; ClrLeaveCriticalSection(void *)
0x18003f1b7  nop
0x18003f1b8  test    r14d, r14d
0x18003f1bb  jnz     short loc_18003F1C5
0x18003f1bd  test    ebx, ebx
0x18003f1bf  jns     loc_18003F044
0x18003f1c5  mov     rcx, [rbp+hLibModule]; hLibModule
0x18003f1c9  call    cs:__imp_FreeLibrary
0x18003f1cf  jmp     loc_18003F044
```
