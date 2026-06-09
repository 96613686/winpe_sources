# StreamBuildInspectionCallContxt

- ea: `0x140016b10`
- end: `0x140016c7a`
- name: `StreamBuildInspectionCallContxt`
- size: `362`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x140016280`
- `0x140016620`
- `0x140017d90`
- `0x140018080`

## callees

- `0x140016b10`
- `0x14001771c`
- `0x14004efd4`

## import_xrefs

- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140016b45`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140016b45`

## string_xrefs

- `0x140016bd2`: `WfpAllocateFromPerProcessorLookasideList`
- `0x140016c55`: `WfpAllocateFromPerProcessorLookasideList`

## pseudocode

```c
__int64 __fastcall StreamBuildInspectionCallContxt(_QWORD *a1)
{
  char *v2; // rbx
  _OWORD *v3; // rax

  v2 = (char *)xmmword_14009AA10 + 128 * (unsigned __int64)(unsigned int)(HIDWORD(KeGetPcr()[1].LockArray) + 1);
  if ( !v2[176] )
    PplpLazyInitializeLookasideList(xmmword_14009AA10, v2 + 64);
  v3 = ExAllocateFromLookasideListEx((PLOOKASIDE_LIST_EX)(v2 + 64));
  if ( v3 )
  {
    *v3 = 0;
    v3[1] = 0;
    v3[2] = 0;
    v3[3] = 0;
    v3[4] = 0;
    v3[5] = 0;
    v3[6] = 0;
    *((_QWORD *)v3 + 14) = 0;
    *a1 = v3;
    return 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
    {
      WPP_SF_sd(
        WPP_GLOBAL_Control->AttachedDevice,
        10,
        (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
        (unsigned int)"WfpAllocateFromPerProcessorLookasideList",
        23);
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 2u && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
        WPP_SF_sd(
          WPP_GLOBAL_Control->AttachedDevice,
          15,
          (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
          (unsigned int)"WfpAllocateFromPerProcessorLookasideList",
          23);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
      {
        WPP_SF_sd(
          WPP_GLOBAL_Control->AttachedDevice,
          15,
          (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
          (unsigned int)"StreamBuildInspectionCallContxt",
          23);
      }
    }
    return -1073741801;
  }
}

```

## disassembly

```asm
0x140016b10  mov     [rsp+arg_0], rbx
0x140016b15  push    rdi
0x140016b16  sub     rsp, 30h
0x140016b1a  mov     eax, gs:1A4h
0x140016b22  mov     rdi, rcx
0x140016b25  mov     rcx, qword ptr cs:xmmword_14009AA10
0x140016b2c  lea     ebx, [rax+1]
0x140016b2f  shl     rbx, 7
0x140016b33  add     rbx, rcx
0x140016b36  movzx   eax, byte ptr [rbx+0B0h]
0x140016b3d  test    al, al
0x140016b3f  jz      short loc_140016B8B
0x140016b41  lea     rcx, [rbx+40h]; Lookaside
0x140016b45  call    cs:__imp_ExAllocateFromLookasideListEx
0x140016b4c  nop     dword ptr [rax+rax+00h]
0x140016b51  test    rax, rax
0x140016b54  jz      short loc_140016B96
0x140016b56  xorps   xmm0, xmm0
0x140016b59  xor     ecx, ecx
0x140016b5b  movups  xmmword ptr [rax], xmm0
0x140016b5e  movups  xmmword ptr [rax+10h], xmm0
0x140016b62  movups  xmmword ptr [rax+20h], xmm0
0x140016b66  movups  xmmword ptr [rax+30h], xmm0
0x140016b6a  movups  xmmword ptr [rax+40h], xmm0
0x140016b6e  movups  xmmword ptr [rax+50h], xmm0
0x140016b72  movups  xmmword ptr [rax+60h], xmm0
0x140016b76  mov     [rax+70h], rcx
0x140016b7a  mov     [rdi], rax
0x140016b7d  xor     eax, eax
0x140016b7f  mov     rbx, [rsp+38h+arg_0]
0x140016b84  add     rsp, 30h
0x140016b88  pop     rdi
0x140016b89  retn
0x140016b8b  lea     rdx, [rbx+40h]
0x140016b8f  call    PplpLazyInitializeLookasideList
0x140016b94  jmp     short loc_140016B41
0x140016b96  mov     rcx, cs:WPP_GLOBAL_Control
0x140016b9d  lea     rbx, WPP_GLOBAL_Control
0x140016ba4  cmp     rcx, rbx
0x140016ba7  jz      short loc_140016BB3
0x140016ba9  cmp     byte ptr [rcx+29h], 2
0x140016bad  jnb     loc_140016C44
0x140016bb3  mov     rcx, cs:WPP_GLOBAL_Control
0x140016bba  cmp     rcx, rbx
0x140016bbd  jz      short loc_140016C31
0x140016bbf  cmp     byte ptr [rcx+29h], 2
0x140016bc3  jb      short loc_140016BF2
0x140016bc5  test    dword ptr [rcx+2Ch], 1000h
0x140016bcc  jz      short loc_140016BF2
0x140016bce  mov     rcx, [rcx+18h]
0x140016bd2  lea     r9, aWfpallocatefro_0; "WfpAllocateFromPerProcessorLookasideLis"...
0x140016bd9  mov     edx, 0Fh
0x140016bde  mov     [rsp+38h+var_18], 0C0000017h
0x140016be6  lea     r8, WPP_dc97c17fd6903ad537f842808d057dba_Traceguids
0x140016bed  call    WPP_SF_sd
0x140016bf2  mov     rcx, cs:WPP_GLOBAL_Control
0x140016bf9  cmp     rcx, rbx
0x140016bfc  jz      short loc_140016C31
0x140016bfe  cmp     byte ptr [rcx+29h], 2
0x140016c02  jb      short loc_140016C31
0x140016c04  test    dword ptr [rcx+2Ch], 1000h
0x140016c0b  jz      short loc_140016C31
0x140016c0d  mov     rcx, [rcx+18h]
0x140016c11  lea     r9, aStreambuildins; "StreamBuildInspectionCallContxt"
0x140016c18  mov     edx, 0Fh
0x140016c1d  mov     [rsp+38h+var_18], 0C0000017h
0x140016c25  lea     r8, WPP_dc97c17fd6903ad537f842808d057dba_Traceguids
0x140016c2c  call    WPP_SF_sd
0x140016c31  mov     rbx, [rsp+38h+arg_0]
0x140016c36  mov     rax, 0FFFFFFFFC0000017h
0x140016c3d  add     rsp, 30h
0x140016c41  pop     rdi
0x140016c42  retn
0x140016c44  test    dword ptr [rcx+2Ch], 1000h
0x140016c4b  jz      loc_140016BB3
0x140016c51  mov     rcx, [rcx+18h]
0x140016c55  lea     r9, aWfpallocatefro_0; "WfpAllocateFromPerProcessorLookasideLis"...
0x140016c5c  mov     edx, 0Ah
0x140016c61  mov     [rsp+38h+var_18], 0C0000017h
0x140016c69  lea     r8, WPP_dc97c17fd6903ad537f842808d057dba_Traceguids
0x140016c70  call    WPP_SF_sd
0x140016c75  jmp     loc_140016BB3
```
