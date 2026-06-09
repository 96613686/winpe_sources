# Csl::DismHelper::IsFeatureInstalled(ushort const *,bool &)

- ea: `0x140021510`
- end: `0x1400215a7`
- name: `?IsFeatureInstalled@DismHelper@Csl@@QEAAJPEBGAEA_N@Z`
- size: `151`
- prototype: `__int64 __fastcall(Csl::DismHelper *__hidden this, const unsigned __int16 *, bool *)`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x140021390`
- `0x140021444`

## callees

- `0x140006fe4`
- `0x140021510`

## import_xrefs

- `DismApi!DismDelete` at `0x14002156f`
- `DismApi!DismDelete` at `0x14002158d`
- `DismApi!DismDelete` at `0x14002156f`
- `DismApi!DismDelete` at `0x14002158d`
- `DismApi!DismGetFeatureInfo` at `0x14002153a`
- `DismApi!DismGetFeatureInfo` at `0x14002153a`

## pseudocode

```c
__int64 __fastcall Csl::DismHelper::IsFeatureInstalled(Csl::DismHelper *this, const unsigned __int16 *a2, bool *a3)
{
  __int64 v3; // rcx
  int FeatureInfo; // eax
  unsigned int v6; // ebx
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  __int64 v9; // [rsp+40h] [rbp+8h] BYREF

  v3 = *(unsigned int *)this;
  v9 = 0;
  FeatureInfo = DismGetFeatureInfo(v3, a2, 0, 1);
  v6 = FeatureInfo;
  if ( FeatureInfo >= 0 )
  {
    *a3 = *(_DWORD *)(v9 + 8) == 4;
    DismDelete();
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x81,
      (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\csldism.cpp",
      (const char *)(unsigned int)FeatureInfo,
      (int)&v9);
    if ( v9 )
      DismDelete();
    return v6;
  }
}

```

## disassembly

```asm
0x140021510  mov     r11, rsp
0x140021513  mov     [r11+10h], rbx
0x140021517  push    rdi
0x140021518  sub     rsp, 30h
0x14002151c  mov     ecx, [rcx]
0x14002151e  lea     rax, [r11+8]
0x140021522  mov     rdi, r8
0x140021525  mov     [r11-18h], rax
0x140021529  xor     r8d, r8d
0x14002152c  mov     qword ptr [r11+8], 0
0x140021534  mov     r9d, 1
0x14002153a  call    cs:__imp_DismGetFeatureInfo
0x140021541  nop     dword ptr [rax+rax+00h]
0x140021546  mov     ebx, eax
0x140021548  test    eax, eax
0x14002154a  jns     short loc_14002157F
0x14002154c  mov     rcx, [rsp+38h]; this
0x140021551  lea     r8, aOnecoreBaseGen_4; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x140021558  mov     r9d, eax; char *
0x14002155b  mov     edx, 81h; void *
0x140021560  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140021565  mov     rcx, [rsp+38h+arg_0]
0x14002156a  test    rcx, rcx
0x14002156d  jz      short loc_14002157B
0x14002156f  call    cs:__imp_DismDelete
0x140021576  nop     dword ptr [rax+rax+00h]
0x14002157b  mov     eax, ebx
0x14002157d  jmp     short loc_14002159B
0x14002157f  mov     rcx, [rsp+38h+arg_0]
0x140021584  cmp     dword ptr [rcx+8], 4
0x140021588  setz    al
0x14002158b  mov     [rdi], al
0x14002158d  call    cs:__imp_DismDelete
0x140021594  nop     dword ptr [rax+rax+00h]
0x140021599  xor     eax, eax
0x14002159b  mov     rbx, [rsp+38h+arg_8]
0x1400215a0  add     rsp, 30h
0x1400215a4  pop     rdi
0x1400215a5  retn
```
