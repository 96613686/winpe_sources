# NetioFreeMdl

- ea: `0x140015f60`
- end: `0x140016047`
- name: `NetioFreeMdl`
- size: `231`
- prototype: `void __stdcall(PMDL Mdl)`
- caller_count: `7`
- callee_count: `4`
- tags: `authz_impersonation, installer_update`

## callers

- `0x140015e70`
- `0x140015ed0`
- `0x14002f720`
- `0x14003c620`
- `0x14003c940`
- `0x140044040`
- `0x140046cb0`

## callees

- `0x140015f60`
- `0x140016258`
- `0x1400174c0`
- `0x14001771c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140016013`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016013`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140015fb7`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140015fb7`

## pseudocode

```c
void __fastcall NetioFreeMdl(char *Mdl)
{
  struct _MDL *v2; // rdi
  char *v3; // rbx
  PMDL v4; // rdx
  struct _LOOKASIDE_LIST_EX *v5; // rcx
  __int64 v6; // rcx
  unsigned __int64 v7; // rdi

  if ( _bittest16((const signed __int16 *)Mdl + 5, 0xCu) )
  {
    v6 = *((_QWORD *)Mdl + 7);
    v7 = v6 + ((unsigned __int64)*((unsigned __int16 *)Mdl + 6) << 7);
    if ( !*(_BYTE *)(v7 + 304) )
      PplpLazyInitializeLookasideList(v6, v7 + 192);
    v4 = (PMDL)Mdl;
    v5 = (struct _LOOKASIDE_LIST_EX *)(v7 + 192);
    goto LABEL_7;
  }
  v2 = (struct _MDL *)(Mdl - 8);
  if ( *(Mdl - 8) == 1 )
  {
    if ( !(unsigned int)Feature_Servicing_TCPIPPPLOptimization__private_IsEnabledDeviceUsageInline() )
    {
      v3 = (char *)NetioNetBufferDataPool + 128 * (unsigned __int64)(unsigned int)(HIDWORD(KeGetPcr()[1].LockArray) + 1);
      if ( !v3[176] )
        PplpLazyInitializeLookasideList((__int64)NetioNetBufferDataPool, (__int64)(v3 + 64));
      v4 = v2;
      v5 = (struct _LOOKASIDE_LIST_EX *)(v3 + 64);
LABEL_7:
      ExFreeToLookasideListEx(v5, v4);
      return;
    }
    PplFreeToLookasideListProcessor((__int64)NetioNetBufferDataPool, v2, *((unsigned __int16 *)Mdl + 6));
  }
  else
  {
    ExFreePoolWithTag(Mdl - 8, 0);
  }
}

```

## disassembly

```asm
0x140015f60  mov     [rsp+arg_0], rbx
0x140015f65  push    rdi
0x140015f66  sub     rsp, 20h
0x140015f6a  bt      word ptr [rcx+0Ah], 0Ch
0x140015f70  mov     rbx, rcx
0x140015f73  jb      short loc_140015FCF
0x140015f75  cmp     byte ptr [rcx-8], 1
0x140015f79  lea     rdi, [rcx-8]
0x140015f7d  jnz     loc_14001600E
0x140015f83  call    Feature_Servicing_TCPIPPPLOptimization__private_IsEnabledDeviceUsageInline
0x140015f88  mov     rcx, cs:NetioNetBufferDataPool
0x140015f8f  test    eax, eax
0x140015f91  jnz     short loc_140015FF5
0x140015f93  mov     eax, gs:1A4h
0x140015f9b  lea     ebx, [rax+1]
0x140015f9e  shl     rbx, 7
0x140015fa2  add     rbx, rcx
0x140015fa5  movzx   eax, byte ptr [rbx+0B0h]
0x140015fac  test    al, al
0x140015fae  jz      short loc_14001602B
0x140015fb0  mov     rdx, rdi; Entry
0x140015fb3  lea     rcx, [rbx+40h]; Lookaside
0x140015fb7  call    cs:__imp_ExFreeToLookasideListEx
0x140015fbe  nop     dword ptr [rax+rax+00h]
0x140015fc3  mov     rbx, [rsp+28h+arg_0]
0x140015fc8  add     rsp, 20h
0x140015fcc  pop     rdi
0x140015fcd  retn
0x140015fcf  movzx   edi, word ptr [rbx+0Ch]
0x140015fd3  mov     rcx, [rcx+38h]
0x140015fd7  shl     rdi, 7
0x140015fdb  add     rdi, rcx
0x140015fde  movzx   eax, byte ptr [rdi+130h]
0x140015fe5  test    al, al
0x140015fe7  jz      short loc_140016039
0x140015fe9  mov     rdx, rbx
0x140015fec  lea     rcx, [rdi+0C0h]
0x140015ff3  jmp     short loc_140015FB7
0x140015ff5  movzx   r8d, word ptr [rbx+0Ch]
0x140015ffa  mov     rdx, rdi
0x140015ffd  call    PplFreeToLookasideListProcessor
0x140016002  mov     rbx, [rsp+28h+arg_0]
0x140016007  add     rsp, 20h
0x14001600b  pop     rdi
0x14001600c  retn
0x14001600e  xor     edx, edx; Tag
0x140016010  mov     rcx, rdi; P
0x140016013  call    cs:__imp_ExFreePoolWithTag
0x14001601a  nop     dword ptr [rax+rax+00h]
0x14001601f  mov     rbx, [rsp+28h+arg_0]
0x140016024  add     rsp, 20h
0x140016028  pop     rdi
0x140016029  retn
0x14001602b  lea     rdx, [rbx+40h]
0x14001602f  call    PplpLazyInitializeLookasideList
0x140016034  jmp     loc_140015FB0
0x140016039  lea     rdx, [rdi+0C0h]
0x140016040  call    PplpLazyInitializeLookasideList
0x140016045  jmp     short loc_140015FE9
```
