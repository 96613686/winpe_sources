# OneXCreateDefaultProfileWithEapMethodId

- ea: `0x18002c450`
- end: `0x18002c640`
- name: `OneXCreateDefaultProfileWithEapMethodId`
- size: `496`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18002c3b0`

## callees

- `0x180005440`
- `0x180010ae0`
- `0x1800214f0`
- `0x18002c450`
- `0x18002ec50`

## import_xrefs

- `MobileNetworking!SetBufferAndLength` at `0x18002c59d`
- `MobileNetworking!SetBufferAndLength` at `0x18002c59d`
- `MobileNetworking!FreeMemory` at `0x18002c602`
- `MobileNetworking!FreeMemory` at `0x18002c602`

## pseudocode

```c
__int64 __fastcall OneXCreateDefaultProfileWithEapMethodId(int a1, char a2, signed int a3, _DWORD *a4, _QWORD *a5)
{
  _QWORD *v9; // rcx
  unsigned int v10; // ebx
  __int64 v11; // rdx
  __int64 v12; // r9
  _QWORD *v13; // rdi
  unsigned int v14; // eax
  void *v16[9]; // [rsp+20h] [rbp-48h] BYREF
  unsigned int v17; // [rsp+70h] [rbp+8h] BYREF

  v16[0] = 0;
  v17 = 0;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 19, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids);
      v9 = WPP_GLOBAL_Control;
    }
    if ( v9 != &WPP_GLOBAL_Control && (*((_DWORD *)v9 + 17) & 0x100) != 0 )
    {
      WPP_SF_(v9[7], 20, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids);
      v9 = WPP_GLOBAL_Control;
    }
  }
  if ( a1 == 1 )
  {
    if ( a3 < 2 )
    {
      v13 = a5;
      if ( !a5 || !a4 )
      {
        v10 = 87;
        if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 68) & 1) != 0 )
        {
          WPP_SF_(v9[7], 23, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids);
          goto LABEL_31;
        }
        goto LABEL_32;
      }
      *a4 = 0;
      *v13 = 0;
      v14 = OneXHlpCreateDefaultProfile(v16, &v17, a3, a2);
      v10 = v14;
      if ( v14 )
      {
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
          goto LABEL_32;
        v11 = 24;
      }
      else
      {
        v14 = SetBufferAndLength(v13, a4, v16[0], v17);
        v10 = v14;
        if ( !v14 )
          goto LABEL_31;
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
          goto LABEL_32;
        v11 = 25;
      }
      v12 = v14;
      goto LABEL_12;
    }
    v10 = 87;
    if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 68) & 1) != 0 )
    {
      v11 = 22;
      goto LABEL_11;
    }
  }
  else
  {
    v10 = 50;
    if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 68) & 1) != 0 )
    {
      v11 = 21;
LABEL_11:
      v12 = v10;
LABEL_12:
      WPP_SF_d(v9[7], v11, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids, v12);
LABEL_31:
      v9 = WPP_GLOBAL_Control;
    }
  }
LABEL_32:
  if ( v16[0] )
  {
    FreeMemory(v16, "OneXHlpFreeMemory", 414);
    v9 = WPP_GLOBAL_Control;
  }
  if ( v9 != &WPP_GLOBAL_Control && (*((_DWORD *)v9 + 17) & 0x800) != 0 )
    WPP_SF_D(v9[7], 26, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids, v10);
  return v10;
}

```

## disassembly

```asm
0x18002c450  push    rbx
0x18002c452  push    rbp
0x18002c453  push    rsi
0x18002c454  push    rdi
0x18002c455  push    r12
0x18002c457  push    r15
0x18002c459  sub     rsp, 38h
0x18002c45d  mov     rsi, r9
0x18002c460  mov     [rsp+68h+var_48], 0
0x18002c469  mov     ebx, r8d
0x18002c46c  mov     [rsp+68h+arg_0], 0
0x18002c474  mov     bpl, dl
0x18002c477  mov     edi, ecx
0x18002c479  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c480  lea     r15, WPP_GLOBAL_Control
0x18002c487  lea     r12, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids
0x18002c48e  cmp     rcx, r15
0x18002c491  jz      short loc_18002C4DA
0x18002c493  test    dword ptr [rcx+44h], 800h
0x18002c49a  jz      short loc_18002C4B4
0x18002c49c  mov     rcx, [rcx+38h]
0x18002c4a0  mov     edx, 13h
0x18002c4a5  mov     r8, r12
0x18002c4a8  call    WPP_SF_
0x18002c4ad  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c4b4  cmp     rcx, r15
0x18002c4b7  jz      short loc_18002C4DA
0x18002c4b9  test    dword ptr [rcx+44h], 100h
0x18002c4c0  jz      short loc_18002C4DA
0x18002c4c2  mov     rcx, [rcx+38h]
0x18002c4c6  mov     edx, 14h
0x18002c4cb  mov     r8, r12
0x18002c4ce  call    WPP_SF_
0x18002c4d3  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c4da  cmp     edi, 1
0x18002c4dd  jz      short loc_18002C50E
0x18002c4df  mov     ebx, 32h ; '2'
0x18002c4e4  cmp     rcx, r15
0x18002c4e7  jz      loc_18002C5E8
0x18002c4ed  test    byte ptr [rcx+44h], 1
0x18002c4f1  jz      loc_18002C5E8
0x18002c4f7  lea     edx, [rbx-1Dh]
0x18002c4fa  mov     r9d, ebx
0x18002c4fd  mov     rcx, [rcx+38h]
0x18002c501  mov     r8, r12
0x18002c504  call    WPP_SF_d
0x18002c509  jmp     loc_18002C5E1
0x18002c50e  cmp     ebx, 2
0x18002c511  jl      short loc_18002C530
0x18002c513  mov     ebx, 57h ; 'W'
0x18002c518  cmp     rcx, r15
0x18002c51b  jz      loc_18002C5E8
0x18002c521  test    byte ptr [rcx+44h], 1
0x18002c525  jz      loc_18002C5E8
0x18002c52b  lea     edx, [rbx-41h]
0x18002c52e  jmp     short loc_18002C4FA
0x18002c530  mov     rdi, [rsp+68h+arg_20]
0x18002c538  test    rdi, rdi
0x18002c53b  jz      loc_18002C5C2
0x18002c541  test    rsi, rsi
0x18002c544  jz      short loc_18002C5C2
0x18002c546  mov     dword ptr [rsi], 0
0x18002c54c  lea     rdx, [rsp+68h+arg_0]
0x18002c551  mov     r9b, bpl
0x18002c554  mov     qword ptr [rdi], 0
0x18002c55b  mov     r8d, ebx
0x18002c55e  lea     rcx, [rsp+68h+var_48]
0x18002c563  call    OneXHlpCreateDefaultProfile
0x18002c568  mov     ebx, eax
0x18002c56a  test    eax, eax
0x18002c56c  jz      short loc_18002C58D
0x18002c56e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c575  cmp     rcx, r15
0x18002c578  jz      short loc_18002C5E8
0x18002c57a  test    byte ptr [rcx+44h], 1
0x18002c57e  jz      short loc_18002C5E8
0x18002c580  mov     edx, 18h
0x18002c585  mov     r9d, eax
0x18002c588  jmp     loc_18002C4FD
0x18002c58d  mov     r9d, [rsp+68h+arg_0]
0x18002c592  mov     rdx, rsi
0x18002c595  mov     r8, [rsp+68h+var_48]
0x18002c59a  mov     rcx, rdi
0x18002c59d  call    cs:__imp_SetBufferAndLength
0x18002c5a3  mov     ebx, eax
0x18002c5a5  test    eax, eax
0x18002c5a7  jz      short loc_18002C5E1
0x18002c5a9  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c5b0  cmp     rcx, r15
0x18002c5b3  jz      short loc_18002C5E8
0x18002c5b5  test    byte ptr [rcx+44h], 1
0x18002c5b9  jz      short loc_18002C5E8
0x18002c5bb  mov     edx, 19h
0x18002c5c0  jmp     short loc_18002C585
0x18002c5c2  mov     ebx, 57h ; 'W'
0x18002c5c7  cmp     rcx, r15
0x18002c5ca  jz      short loc_18002C5E8
0x18002c5cc  test    byte ptr [rcx+44h], 1
0x18002c5d0  jz      short loc_18002C5E8
0x18002c5d2  mov     rcx, [rcx+38h]
0x18002c5d6  lea     edx, [rbx-40h]
0x18002c5d9  mov     r8, r12
0x18002c5dc  call    WPP_SF_
0x18002c5e1  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c5e8  cmp     [rsp+68h+var_48], 0
0x18002c5ee  jz      short loc_18002C60F
0x18002c5f0  mov     r8d, 19Eh
0x18002c5f6  lea     rdx, aOnexhlpfreemem; "OneXHlpFreeMemory"
0x18002c5fd  lea     rcx, [rsp+68h+var_48]
0x18002c602  call    cs:__imp_FreeMemory
0x18002c608  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c60f  cmp     rcx, r15
0x18002c612  jz      short loc_18002C631
0x18002c614  test    dword ptr [rcx+44h], 800h
0x18002c61b  jz      short loc_18002C631
0x18002c61d  mov     rcx, [rcx+38h]
0x18002c621  mov     edx, 1Ah
0x18002c626  mov     r9d, ebx
0x18002c629  mov     r8, r12
0x18002c62c  call    WPP_SF_D
0x18002c631  mov     eax, ebx
0x18002c633  add     rsp, 38h
0x18002c637  pop     r15
0x18002c639  pop     r12
0x18002c63b  pop     rdi
0x18002c63c  pop     rsi
0x18002c63d  pop     rbp
0x18002c63e  pop     rbx
0x18002c63f  retn
```
