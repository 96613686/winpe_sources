# ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::LoadStringW(uint)

- ea: `0x18000a280`
- end: `0x18000a384`
- name: `?LoadStringW@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHI@Z`
- size: `260`
- prototype: `__int64 __fastcall(ATL::CAtlBaseModule *, unsigned int)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x1800092dc`
- `0x180009e04`
- `0x180009f4c`
- `0x18000ee48`

## callees

- `0x18000a280`
- `0x18000a38c`
- `0x18000d8a4`

## import_xrefs

- `KERNEL32!LockResource` at `0x18000a2f4`
- `KERNEL32!LockResource` at `0x18000a2f4`
- `KERNEL32!SizeofResource` at `0x18000a308`
- `KERNEL32!SizeofResource` at `0x18000a308`
- `KERNEL32!FindResourceExW` at `0x18000a2ce`
- `KERNEL32!FindResourceExW` at `0x18000a2ce`
- `KERNEL32!LoadResource` at `0x18000a2e2`
- `KERNEL32!LoadResource` at `0x18000a2e2`

## pseudocode

```c
__int64 __fastcall ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::LoadStringW(
        ATL::CAtlBaseModule *a1,
        unsigned int a2)
{
  HMODULE HInstanceAt; // rdi
  int v5; // ebp
  HRSRC Resource; // rax
  ATL::CAtlBaseModule *v7; // rcx
  HRSRC v8; // rsi
  HGLOBAL v9; // rax
  __int64 v10; // rax
  ATL::CAtlBaseModule *v11; // rbx
  int v12; // edx
  int v13; // edx

  HInstanceAt = ATL::CAtlBaseModule::GetHInstanceAt(a1, 0);
  v5 = 1;
  if ( !HInstanceAt )
    return 0;
  while ( 1 )
  {
    Resource = FindResourceExW(HInstanceAt, (LPCWSTR)6, (LPCWSTR)(unsigned __int16)((a2 >> 4) + 1), 0);
    v8 = Resource;
    if ( Resource )
      break;
LABEL_12:
    v13 = v5++;
    HInstanceAt = ATL::CAtlBaseModule::GetHInstanceAt(v7, v13);
    if ( !HInstanceAt )
      return 0;
  }
  v9 = LoadResource(HInstanceAt, Resource);
  if ( !v9 )
    goto LABEL_4;
  v11 = (ATL::CAtlBaseModule *)LockResource(v9);
  if ( !v11 )
    goto LABEL_4;
  v7 = (ATL::CAtlBaseModule *)((char *)v11 + SizeofResource(HInstanceAt, v8));
  v12 = a2 & 0xF;
  if ( (a2 & 0xF) != 0 )
  {
    while ( v11 < v7 )
    {
      v11 = (ATL::CAtlBaseModule *)((char *)v11 + 2 * *(unsigned __int16 *)v11 + 2);
      if ( !--v12 )
        goto LABEL_9;
    }
    goto LABEL_4;
  }
LABEL_9:
  if ( v11 >= v7 )
  {
LABEL_4:
    v10 = 0;
    goto LABEL_11;
  }
  v10 = (unsigned __int64)v11 & -(__int64)(*(_WORD *)v11 != 0);
LABEL_11:
  if ( !v10 )
    goto LABEL_12;
  return ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::LoadStringW(
           a1,
           HInstanceAt,
           a2);
}

```

## disassembly

```asm
0x18000a280  push    rbx
0x18000a282  push    rbp
0x18000a283  push    rsi
0x18000a284  push    rdi
0x18000a285  push    r12
0x18000a287  push    r13
0x18000a289  push    r14
0x18000a28b  push    r15
0x18000a28d  sub     rsp, 28h
0x18000a291  mov     r14d, edx
0x18000a294  mov     r15, rcx
0x18000a297  xor     edx, edx; int
0x18000a299  call    ?GetHInstanceAt@CAtlBaseModule@ATL@@QEAAPEAUHINSTANCE__@@H@Z; ATL::CAtlBaseModule::GetHInstanceAt(int)
0x18000a29e  mov     r13d, 1
0x18000a2a4  mov     rdi, rax
0x18000a2a7  mov     ebp, r13d
0x18000a2aa  test    rax, rax
0x18000a2ad  jz      loc_18000A35C
0x18000a2b3  mov     eax, r14d
0x18000a2b6  shr     eax, 4
0x18000a2b9  add     ax, r13w
0x18000a2bd  movzx   r12d, ax
0x18000a2c1  xor     r9d, r9d; wLanguage
0x18000a2c4  mov     r8, r12; lpName
0x18000a2c7  mov     rcx, rdi; hModule
0x18000a2ca  lea     edx, [r9+6]; lpType
0x18000a2ce  call    cs:__imp_FindResourceExW
0x18000a2d4  mov     rsi, rax
0x18000a2d7  test    rax, rax
0x18000a2da  jz      short loc_18000A346
0x18000a2dc  mov     rdx, rax; hResInfo
0x18000a2df  mov     rcx, rdi; hModule
0x18000a2e2  call    cs:__imp_LoadResource
0x18000a2e8  test    rax, rax
0x18000a2eb  jnz     short loc_18000A2F1
0x18000a2ed  xor     eax, eax
0x18000a2ef  jmp     short loc_18000A341
0x18000a2f1  mov     rcx, rax; hResData
0x18000a2f4  call    cs:__imp_LockResource
0x18000a2fa  mov     rbx, rax
0x18000a2fd  test    rax, rax
0x18000a300  jz      short loc_18000A2ED
0x18000a302  mov     rdx, rsi; hResInfo
0x18000a305  mov     rcx, rdi; hModule
0x18000a308  call    cs:__imp_SizeofResource
0x18000a30e  mov     ecx, eax
0x18000a310  mov     edx, r14d
0x18000a313  add     rcx, rbx; this
0x18000a316  and     edx, 0Fh
0x18000a319  jbe     short loc_18000A330
0x18000a31b  cmp     rbx, rcx
0x18000a31e  jnb     short loc_18000A2ED
0x18000a320  movzx   eax, word ptr [rbx]
0x18000a323  lea     rbx, [rbx+rax*2]
0x18000a327  add     rbx, 2
0x18000a32b  add     edx, 0FFFFFFFFh
0x18000a32e  jnz     short loc_18000A31B
0x18000a330  cmp     rbx, rcx
0x18000a333  jnb     short loc_18000A2ED
0x18000a335  movzx   eax, word ptr [rbx]
0x18000a338  neg     ax
0x18000a33b  sbb     rax, rax
0x18000a33e  and     rax, rbx
0x18000a341  test    rax, rax
0x18000a344  jnz     short loc_18000A36F
0x18000a346  mov     edx, ebp; int
0x18000a348  add     ebp, r13d
0x18000a34b  call    ?GetHInstanceAt@CAtlBaseModule@ATL@@QEAAPEAUHINSTANCE__@@H@Z; ATL::CAtlBaseModule::GetHInstanceAt(int)
0x18000a350  mov     rdi, rax
0x18000a353  test    rax, rax
0x18000a356  jnz     loc_18000A2C1
0x18000a35c  xor     eax, eax
0x18000a35e  add     rsp, 28h
0x18000a362  pop     r15
0x18000a364  pop     r14
0x18000a366  pop     r13
0x18000a368  pop     r12
0x18000a36a  pop     rdi
0x18000a36b  pop     rsi
0x18000a36c  pop     rbp
0x18000a36d  pop     rbx
0x18000a36e  retn
0x18000a36f  test    rdi, rdi
0x18000a372  jz      short loc_18000A35C
0x18000a374  mov     r8d, r14d
0x18000a377  mov     rdx, rdi
0x18000a37a  mov     rcx, r15
0x18000a37d  call    ?LoadStringW@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHPEAUHINSTANCE__@@I@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::LoadStringW(HINSTANCE__ *,uint)
0x18000a382  jmp     short loc_18000A35E
```
