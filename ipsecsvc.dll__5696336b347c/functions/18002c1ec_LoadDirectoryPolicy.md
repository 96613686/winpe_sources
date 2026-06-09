# LoadDirectoryPolicy

- ea: `0x18002c1ec`
- end: `0x18002c37a`
- name: `LoadDirectoryPolicy`
- size: `398`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `3`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002c9b0`
- `0x18002cf74`
- `0x18002d64c`

## callees

- `0x180006f60`
- `0x18000e510`
- `0x18000f638`
- `0x180019d80`
- `0x18002c1ec`
- `0x18002da00`
- `0x18003eaa8`
- `0x18003eac4`
- `0x18003f168`
- `0x18003ff4c`

## pseudocode

```c
__int64 __fastcall LoadDirectoryPolicy(__int64 a1, _QWORD *a2)
{
  unsigned int PolicyObjectFromDirectory; // eax
  unsigned int v5; // ebx
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // rdx
  __int64 v9; // r8
  LPVOID lpMem; // [rsp+70h] [rbp+18h] BYREF
  LDAP *v12; // [rsp+78h] [rbp+20h]

  lpMem = 0;
  v12 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids);
  PolicyObjectFromDirectory = ComputeDefaultDirectory((__int64 *)&lpMem);
  v5 = PolicyObjectFromDirectory;
  if ( PolicyObjectFromDirectory )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v7 = 29;
LABEL_16:
        WPP_SF_d(v6[2], v7, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids, PolicyObjectFromDirectory);
        v6 = WPP_GLOBAL_Control;
        goto LABEL_17;
      }
      goto LABEL_17;
    }
    goto LABEL_20;
  }
  PolicyObjectFromDirectory = OpenDirectoryServerHandle((LPCWSTR)lpMem);
  v5 = PolicyObjectFromDirectory;
  if ( PolicyObjectFromDirectory )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v7 = 30;
        goto LABEL_16;
      }
LABEL_17:
      if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 0x10) != 0 )
        WPP_SF_SD(v6[2], 33, (unsigned int)WPP_e815f316f4bb38f383997e5feee741ae_Traceguids, a1, v5);
    }
LABEL_20:
    *a2 = 0;
    goto LABEL_24;
  }
  PolicyObjectFromDirectory = ReadPolicyObjectFromDirectory((int)v12, a1);
  v5 = PolicyObjectFromDirectory;
  if ( PolicyObjectFromDirectory )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v7 = 31;
        goto LABEL_16;
      }
      goto LABEL_17;
    }
    goto LABEL_20;
  }
  *a2 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, v9, a1);
LABEL_24:
  if ( lpMem )
    IpsecFreeMem(lpMem);
  if ( v12 )
    CloseDirectoryServerHandle(v12);
  return v5;
}

```

## disassembly

```asm
0x18002c1ec  mov     rax, rsp
0x18002c1ef  mov     [rax+8], rbx
0x18002c1f3  mov     [rax+10h], rsi
0x18002c1f7  push    r12
0x18002c1f9  push    r14
0x18002c1fb  push    r15
0x18002c1fd  sub     rsp, 40h
0x18002c201  mov     r14, rdx
0x18002c204  mov     qword ptr [rax+18h], 0
0x18002c20c  mov     rsi, rcx
0x18002c20f  mov     qword ptr [rax+20h], 0
0x18002c217  mov     qword ptr [rax-28h], 0
0x18002c21f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c226  lea     r15, WPP_GLOBAL_Control
0x18002c22d  lea     r12, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids
0x18002c234  cmp     rcx, r15
0x18002c237  jz      short loc_18002C250
0x18002c239  test    byte ptr [rcx+1Ch], 4
0x18002c23d  jz      short loc_18002C250
0x18002c23f  mov     rcx, [rcx+10h]
0x18002c243  mov     edx, 1Ch
0x18002c248  mov     r8, r12
0x18002c24b  call    WPP_SF_
0x18002c250  lea     rcx, [rsp+58h+lpMem]
0x18002c255  call    ComputeDefaultDirectory
0x18002c25a  mov     ebx, eax
0x18002c25c  test    eax, eax
0x18002c25e  jz      short loc_18002C27D
0x18002c260  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c267  cmp     rcx, r15
0x18002c26a  jz      loc_18002C313
0x18002c270  test    byte ptr [rcx+1Ch], 10h
0x18002c274  jz      short loc_18002C2F0
0x18002c276  mov     edx, 1Dh
0x18002c27b  jmp     short loc_18002C2DA
0x18002c27d  mov     rcx, [rsp+58h+lpMem]; DomainName
0x18002c282  lea     r8, [rsp+58h+arg_18]
0x18002c287  call    OpenDirectoryServerHandle
0x18002c28c  mov     ebx, eax
0x18002c28e  test    eax, eax
0x18002c290  jz      short loc_18002C2AB
0x18002c292  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c299  cmp     rcx, r15
0x18002c29c  jz      short loc_18002C313
0x18002c29e  test    byte ptr [rcx+1Ch], 10h
0x18002c2a2  jz      short loc_18002C2F0
0x18002c2a4  mov     edx, 1Eh
0x18002c2a9  jmp     short loc_18002C2DA
0x18002c2ab  mov     rcx, [rsp+58h+arg_18]; int
0x18002c2b0  lea     r8, [rsp+58h+var_28]
0x18002c2b5  mov     rdx, rsi; int
0x18002c2b8  call    ReadPolicyObjectFromDirectory
0x18002c2bd  mov     ebx, eax
0x18002c2bf  test    eax, eax
0x18002c2c1  jz      short loc_18002C31C
0x18002c2c3  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c2ca  cmp     rcx, r15
0x18002c2cd  jz      short loc_18002C313
0x18002c2cf  test    byte ptr [rcx+1Ch], 10h
0x18002c2d3  jz      short loc_18002C2F0
0x18002c2d5  mov     edx, 1Fh
0x18002c2da  mov     rcx, [rcx+10h]
0x18002c2de  mov     r9d, eax
0x18002c2e1  mov     r8, r12
0x18002c2e4  call    WPP_SF_d
0x18002c2e9  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c2f0  cmp     rcx, r15
0x18002c2f3  jz      short loc_18002C313
0x18002c2f5  test    byte ptr [rcx+1Ch], 10h
0x18002c2f9  jz      short loc_18002C313
0x18002c2fb  mov     rcx, [rcx+10h]
0x18002c2ff  mov     edx, 21h ; '!'
0x18002c304  mov     r9, rsi
0x18002c307  mov     [rsp+58h+var_38], ebx
0x18002c30b  mov     r8, r12
0x18002c30e  call    WPP_SF_SD
0x18002c313  mov     qword ptr [r14], 0
0x18002c31a  jmp     short loc_18002C342
0x18002c31c  mov     rax, [rsp+58h+var_28]
0x18002c321  mov     [r14], rax
0x18002c324  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c32b  cmp     rcx, r15
0x18002c32e  jz      short loc_18002C342
0x18002c330  test    byte ptr [rcx+1Ch], 4
0x18002c334  jz      short loc_18002C342
0x18002c336  mov     rcx, [rcx+10h]
0x18002c33a  mov     r9, rsi
0x18002c33d  call    WPP_SF_S
0x18002c342  cmp     [rsp+58h+lpMem], 0
0x18002c348  jz      short loc_18002C354
0x18002c34a  mov     rcx, [rsp+58h+lpMem]; lpMem
0x18002c34f  call    IpsecFreeMem
0x18002c354  mov     rcx, [rsp+58h+arg_18]
0x18002c359  test    rcx, rcx
0x18002c35c  jz      short loc_18002C363
0x18002c35e  call    CloseDirectoryServerHandle
0x18002c363  mov     rsi, [rsp+58h+arg_8]
0x18002c368  mov     eax, ebx
0x18002c36a  mov     rbx, [rsp+58h+arg_0]
0x18002c36f  add     rsp, 40h
0x18002c373  pop     r15
0x18002c375  pop     r14
0x18002c377  pop     r12
0x18002c379  retn
```
