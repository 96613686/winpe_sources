# MdaMapDesiredAccess

- ea: `0x140033af0`
- end: `0x140033c4a`
- name: `MdaMapDesiredAccess`
- size: `346`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140030b60`
- `0x1400316d0`

## callees

- `0x1400159fc`
- `0x140033af0`

## pseudocode

```c
__int64 __fastcall MdaMapDesiredAccess(unsigned int a1)
{
  int v1; // r8d
  PDEVICE_OBJECT v3; // r10
  __int64 v4; // rdx

  v1 = a1 & 1;
  if ( (a1 & 1) != 0 || (a1 & 0x20) != 0 )
  {
    if ( (a1 & 2) != 0 || (a1 & 4) != 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 100, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids, a1);
      }
      return 3;
    }
  }
  else if ( (a1 & 2) != 0 || (v1 = 0, (a1 & 4) != 0) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 101, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids, a1);
    }
    return 2;
  }
  if ( (a1 & 0x20) != 0 )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) == 0 )
    {
      return 1;
    }
    v4 = 102;
LABEL_19:
    WPP_SF_d(v3->AttachedDevice, v4, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids, a1);
    return 1;
  }
  if ( v1 )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) == 0 )
    {
      return 1;
    }
    v4 = 103;
    goto LABEL_19;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 104, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids, a1);
  return 0;
}

```

## disassembly

```asm
0x140033af0  sub     rsp, 28h
0x140033af4  mov     edx, ecx
0x140033af6  mov     r8d, ecx
0x140033af9  and     edx, 20h
0x140033afc  and     r8d, 1
0x140033b00  jnz     short loc_140033B54
0x140033b02  test    edx, edx
0x140033b04  jnz     short loc_140033B54
0x140033b06  bt      ecx, 1
0x140033b0a  jb      short loc_140033B15
0x140033b0c  mov     r8d, edx
0x140033b0f  bt      ecx, 2
0x140033b13  jnb     short loc_140033B68
0x140033b15  mov     r10, cs:WPP_GLOBAL_Control
0x140033b1c  lea     rax, WPP_GLOBAL_Control
0x140033b23  cmp     r10, rax
0x140033b26  jz      short loc_140033B4A
0x140033b28  test    dword ptr [r10+2Ch], 40000h
0x140033b30  jz      short loc_140033B4A
0x140033b32  mov     r9d, ecx
0x140033b35  lea     r8, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids
0x140033b3c  mov     rcx, [r10+18h]
0x140033b40  mov     edx, 65h ; 'e'
0x140033b45  call    WPP_SF_d
0x140033b4a  mov     eax, 2
0x140033b4f  jmp     loc_140033C44
0x140033b54  bt      ecx, 1
0x140033b58  jb      loc_140033C0A
0x140033b5e  bt      ecx, 2
0x140033b62  jb      loc_140033C0A
0x140033b68  test    edx, edx
0x140033b6a  jz      short loc_140033B90
0x140033b6c  mov     r10, cs:WPP_GLOBAL_Control
0x140033b73  lea     rax, WPP_GLOBAL_Control
0x140033b7a  cmp     r10, rax
0x140033b7d  jz      short loc_140033BCA
0x140033b7f  test    dword ptr [r10+2Ch], 40000h
0x140033b87  jz      short loc_140033BCA
0x140033b89  mov     edx, 66h ; 'f'
0x140033b8e  jmp     short loc_140033BB7
0x140033b90  test    r8d, r8d
0x140033b93  jz      short loc_140033BD1
0x140033b95  mov     r10, cs:WPP_GLOBAL_Control
0x140033b9c  lea     rax, WPP_GLOBAL_Control
0x140033ba3  cmp     r10, rax
0x140033ba6  jz      short loc_140033BCA
0x140033ba8  test    dword ptr [r10+2Ch], 40000h
0x140033bb0  jz      short loc_140033BCA
0x140033bb2  mov     edx, 67h ; 'g'
0x140033bb7  mov     r9d, ecx
0x140033bba  lea     r8, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids
0x140033bc1  mov     rcx, [r10+18h]
0x140033bc5  call    WPP_SF_d
0x140033bca  mov     eax, 1
0x140033bcf  jmp     short loc_140033C44
0x140033bd1  mov     r10, cs:WPP_GLOBAL_Control
0x140033bd8  lea     rax, WPP_GLOBAL_Control
0x140033bdf  cmp     r10, rax
0x140033be2  jz      short loc_140033C06
0x140033be4  test    dword ptr [r10+2Ch], 40000h
0x140033bec  jz      short loc_140033C06
0x140033bee  mov     r9d, ecx
0x140033bf1  lea     r8, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids
0x140033bf8  mov     rcx, [r10+18h]
0x140033bfc  mov     edx, 68h ; 'h'
0x140033c01  call    WPP_SF_d
0x140033c06  xor     eax, eax
0x140033c08  jmp     short loc_140033C44
0x140033c0a  mov     r10, cs:WPP_GLOBAL_Control
0x140033c11  lea     rax, WPP_GLOBAL_Control
0x140033c18  cmp     r10, rax
0x140033c1b  jz      short loc_140033C3F
0x140033c1d  test    dword ptr [r10+2Ch], 40000h
0x140033c25  jz      short loc_140033C3F
0x140033c27  mov     r9d, ecx
0x140033c2a  lea     r8, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids
0x140033c31  mov     rcx, [r10+18h]
0x140033c35  mov     edx, 64h ; 'd'
0x140033c3a  call    WPP_SF_d
0x140033c3f  mov     eax, 3
0x140033c44  add     rsp, 28h
0x140033c48  retn
```
