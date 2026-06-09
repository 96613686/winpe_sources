# QueryDirCache::ValidateCacheBuffer(uchar *,ulong,ulong)

- ea: `0x140016ba8`
- end: `0x140016d7a`
- name: `?ValidateCacheBuffer@QueryDirCache@@IEAAHPEAEKK@Z`
- size: `466`
- prototype: `__int64 __fastcall(QueryDirCache *__hidden this, unsigned __int8 *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1400169f0`

## callees

- `0x14000324c`
- `0x14000327c`
- `0x1400032c0`
- `0x140016ba8`

## pseudocode

```c
__int64 __fastcall QueryDirCache::ValidateCacheBuffer(
        QueryDirCache *this,
        unsigned __int8 *a2,
        unsigned int a3,
        unsigned int a4)
{
  unsigned int v4; // ebp
  unsigned int v7; // edi
  unsigned __int8 *v8; // r12
  unsigned int v9; // eax
  __int64 v10; // rcx
  PDEVICE_OBJECT v11; // rcx
  __int64 v12; // rdx

  v4 = 4;
  if ( a3 >= 4 )
  {
    v7 = *(_DWORD *)a2;
    if ( *(_DWORD *)a2 && v7 <= a4 )
    {
      v8 = a2 + 4;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 26, WPP_857ee275c9d63dc09dd0836f7968c8e8_Traceguids, v7);
      while ( 1 )
      {
        if ( !v7 )
          return 1;
        v9 = v4 + 8;
        if ( v4 + 8 < v4 )
        {
          v11 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            v12 = 31;
            goto LABEL_32;
          }
          return 0;
        }
        if ( a3 < v9 )
        {
          v11 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            v12 = 27;
            goto LABEL_32;
          }
          return 0;
        }
        v10 = *(unsigned int *)v8;
        if ( (unsigned int)v10 < 8 )
        {
          v11 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            v12 = 28;
            goto LABEL_32;
          }
          return 0;
        }
        v4 += v10;
        if ( v4 < v9 )
          break;
        if ( a3 < v4 )
        {
          v11 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            v12 = 29;
LABEL_32:
            WPP_SF_d(v11->AttachedDevice, v12, WPP_857ee275c9d63dc09dd0836f7968c8e8_Traceguids, *(_DWORD *)a2 - v7);
            return 0;
          }
          return 0;
        }
        v8 += v10;
        --v7;
      }
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v12 = 30;
        goto LABEL_32;
      }
    }
    else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_dd(WPP_GLOBAL_Control->AttachedDevice, 25, WPP_857ee275c9d63dc09dd0836f7968c8e8_Traceguids, v7, a4);
    }
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 24, WPP_857ee275c9d63dc09dd0836f7968c8e8_Traceguids);
  }
  return 0;
}

```

## disassembly

```asm
0x140016ba8  push    rbx
0x140016baa  push    rbp
0x140016bab  push    rdi
0x140016bac  push    r12
0x140016bae  push    r14
0x140016bb0  push    r15
0x140016bb2  sub     rsp, 38h
0x140016bb6  mov     ebp, 4
0x140016bbb  mov     r15d, r8d
0x140016bbe  mov     r14, rdx
0x140016bc1  cmp     r8d, ebp
0x140016bc4  jnb     short loc_140016BFF
0x140016bc6  mov     rcx, cs:WPP_GLOBAL_Control
0x140016bcd  lea     rbx, WPP_GLOBAL_Control
0x140016bd4  cmp     rcx, rbx
0x140016bd7  jz      loc_140016D69
0x140016bdd  cmp     byte ptr [rcx+29h], 2
0x140016be1  jb      loc_140016D69
0x140016be7  mov     rcx, [rcx+18h]
0x140016beb  lea     edx, [rbp+14h]
0x140016bee  lea     r8, WPP_857ee275c9d63dc09dd0836f7968c8e8_Traceguids
0x140016bf5  call    WPP_SF_
0x140016bfa  jmp     loc_140016D69
0x140016bff  mov     edi, [rdx]
0x140016c01  test    edi, edi
0x140016c03  jz      loc_140016D33
0x140016c09  cmp     edi, r9d
0x140016c0c  ja      loc_140016D33
0x140016c12  lea     r12, [rdx+4]
0x140016c16  mov     rcx, cs:WPP_GLOBAL_Control
0x140016c1d  lea     rbx, WPP_GLOBAL_Control
0x140016c24  cmp     rcx, rbx
0x140016c27  jz      short loc_140016C47
0x140016c29  cmp     byte ptr [rcx+29h], 5
0x140016c2d  jb      short loc_140016C47
0x140016c2f  mov     rcx, [rcx+18h]
0x140016c33  lea     r8, WPP_857ee275c9d63dc09dd0836f7968c8e8_Traceguids
0x140016c3a  mov     edx, 1Ah
0x140016c3f  mov     r9d, edi
0x140016c42  call    WPP_SF_d
0x140016c47  test    edi, edi
0x140016c49  jz      loc_140016D2C
0x140016c4f  lea     eax, [rbp+8]
0x140016c52  cmp     eax, ebp
0x140016c54  jb      loc_140016CFD
0x140016c5a  cmp     r15d, eax
0x140016c5d  jb      loc_140016CE4
0x140016c63  mov     ecx, [r12]
0x140016c67  cmp     ecx, 8
0x140016c6a  jb      short loc_140016CC3
0x140016c6c  lea     ebp, [rax-8]
0x140016c6f  add     ebp, ecx
0x140016c71  cmp     ebp, eax
0x140016c73  jb      short loc_140016CA2
0x140016c75  cmp     r15d, ebp
0x140016c78  jb      short loc_140016C81
0x140016c7a  add     r12, rcx
0x140016c7d  dec     edi
0x140016c7f  jmp     short loc_140016C47
0x140016c81  mov     rcx, cs:WPP_GLOBAL_Control
0x140016c88  cmp     rcx, rbx
0x140016c8b  jz      loc_140016D69
0x140016c91  cmp     byte ptr [rcx+29h], 2
0x140016c95  jb      loc_140016D69
0x140016c9b  mov     edx, 1Dh
0x140016ca0  jmp     short loc_140016D14
0x140016ca2  mov     rcx, cs:WPP_GLOBAL_Control
0x140016ca9  cmp     rcx, rbx
0x140016cac  jz      loc_140016D69
0x140016cb2  cmp     byte ptr [rcx+29h], 2
0x140016cb6  jb      loc_140016D69
0x140016cbc  mov     edx, 1Eh
0x140016cc1  jmp     short loc_140016D14
0x140016cc3  mov     rcx, cs:WPP_GLOBAL_Control
0x140016cca  cmp     rcx, rbx
0x140016ccd  jz      loc_140016D69
0x140016cd3  cmp     byte ptr [rcx+29h], 2
0x140016cd7  jb      loc_140016D69
0x140016cdd  mov     edx, 1Ch
0x140016ce2  jmp     short loc_140016D14
0x140016ce4  mov     rcx, cs:WPP_GLOBAL_Control
0x140016ceb  cmp     rcx, rbx
0x140016cee  jz      short loc_140016D69
0x140016cf0  cmp     byte ptr [rcx+29h], 2
0x140016cf4  jb      short loc_140016D69
0x140016cf6  mov     edx, 1Bh
0x140016cfb  jmp     short loc_140016D14
0x140016cfd  mov     rcx, cs:WPP_GLOBAL_Control
0x140016d04  cmp     rcx, rbx
0x140016d07  jz      short loc_140016D69
0x140016d09  cmp     byte ptr [rcx+29h], 2
0x140016d0d  jb      short loc_140016D69
0x140016d0f  mov     edx, 1Fh
0x140016d14  mov     r9d, [r14]
0x140016d17  lea     r8, WPP_857ee275c9d63dc09dd0836f7968c8e8_Traceguids
0x140016d1e  mov     rcx, [rcx+18h]
0x140016d22  sub     r9d, edi
0x140016d25  call    WPP_SF_d
0x140016d2a  jmp     short loc_140016D69
0x140016d2c  mov     eax, 1
0x140016d31  jmp     short loc_140016D6B
0x140016d33  mov     rcx, cs:WPP_GLOBAL_Control
0x140016d3a  lea     rbx, WPP_GLOBAL_Control
0x140016d41  cmp     rcx, rbx
0x140016d44  jz      short loc_140016D69
0x140016d46  cmp     byte ptr [rcx+29h], 2
0x140016d4a  jb      short loc_140016D69
0x140016d4c  mov     rcx, [rcx+18h]
0x140016d50  lea     r8, WPP_857ee275c9d63dc09dd0836f7968c8e8_Traceguids
0x140016d57  mov     [rsp+68h+var_48], r9d
0x140016d5c  mov     edx, 19h
0x140016d61  mov     r9d, edi
0x140016d64  call    WPP_SF_dd
0x140016d69  xor     eax, eax
0x140016d6b  add     rsp, 38h
0x140016d6f  pop     r15
0x140016d71  pop     r14
0x140016d73  pop     r12
0x140016d75  pop     rdi
0x140016d76  pop     rbp
0x140016d77  pop     rbx
0x140016d78  retn
```
