# Csl::DismHelper::Initialize(ushort const *)

- ea: `0x180007e68`
- end: `0x180007ef5`
- name: `?Initialize@DismHelper@Csl@@QEAAJPEBG@Z`
- size: `141`
- prototype: `__int64 __fastcall(Csl::DismHelper *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180006790`

## callees

- `0x1800068d4`
- `0x180007e68`
- `0x180007efc`

## import_xrefs

- `DismApi!DismShutdown` at `0x180007ec1`
- `DismApi!DismShutdown` at `0x180007ec1`
- `DismApi!DismInitialize` at `0x180007e7d`
- `DismApi!DismInitialize` at `0x180007e7d`
- `DismApi!DismOpenSession` at `0x180007eb5`
- `DismApi!DismOpenSession` at `0x180007eb5`

## pseudocode

```c
__int64 __fastcall Csl::DismHelper::Initialize(Csl::DismHelper *this, const unsigned __int16 *a2)
{
  int v3; // ebx
  __int64 v4; // rdx
  int v6; // eax
  unsigned int v7; // r8d
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v3 = DismInitialize(2, 0, 0);
  if ( v3 < 0 )
  {
    v4 = 78;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\csldism.cpp",
      (const char *)(unsigned int)v3,
      v8);
    return (unsigned int)v3;
  }
  v3 = DismOpenSession(L"DISM_{53BFAE52-B167-4E2F-A258-0A37B57FF845}", 0, 0, this);
  if ( v3 < 0 )
  {
    v6 = DismShutdown();
    if ( v6 < 0 )
      wil::details::in1diag3::_Log_Hr(retaddr, (void *)0x57, v7, (const char *)(unsigned int)v6, v8);
    v4 = 88;
    goto LABEL_3;
  }
  *((_BYTE *)this + 4) = 1;
  return 0;
}

```

## disassembly

```asm
0x180007e68  mov     [rsp+arg_0], rbx
0x180007e6d  push    rdi; int
0x180007e6e  sub     rsp, 20h
0x180007e72  xor     edx, edx
0x180007e74  mov     rdi, rcx
0x180007e77  xor     r8d, r8d
0x180007e7a  lea     ecx, [rdx+2]
0x180007e7d  call    cs:__imp_DismInitialize
0x180007e83  mov     ebx, eax
0x180007e85  test    eax, eax
0x180007e87  jns     short loc_180007EA6
0x180007e89  mov     edx, 4Eh ; 'N'; void *
0x180007e8e  mov     rcx, [rsp+28h]; this
0x180007e93  lea     r8, aOnecoreBaseGen; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x180007e9a  mov     r9d, ebx; char *
0x180007e9d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007ea2  mov     eax, ebx
0x180007ea4  jmp     short loc_180007EEA
0x180007ea6  mov     r9, rdi
0x180007ea9  lea     rcx, aDism53bfae52B1; "DISM_{53BFAE52-B167-4E2F-A258-0A37B57FF"...
0x180007eb0  xor     r8d, r8d
0x180007eb3  xor     edx, edx
0x180007eb5  call    cs:__imp_DismOpenSession
0x180007ebb  mov     ebx, eax
0x180007ebd  test    eax, eax
0x180007ebf  jns     short loc_180007EE4
0x180007ec1  call    cs:__imp_DismShutdown
0x180007ec7  test    eax, eax
0x180007ec9  jns     short loc_180007EDD
0x180007ecb  mov     rcx, [rsp+28h]; this
0x180007ed0  mov     r9d, eax; char *
0x180007ed3  mov     edx, 57h ; 'W'; void *
0x180007ed8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180007edd  mov     edx, 58h ; 'X'
0x180007ee2  jmp     short loc_180007E8E
0x180007ee4  mov     byte ptr [rdi+4], 1
0x180007ee8  xor     eax, eax
0x180007eea  mov     rbx, [rsp+28h+arg_0]
0x180007eef  add     rsp, 20h
0x180007ef3  pop     rdi
0x180007ef4  retn
```
