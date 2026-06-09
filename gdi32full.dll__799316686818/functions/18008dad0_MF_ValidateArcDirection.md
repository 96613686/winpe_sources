# MF_ValidateArcDirection

- ea: `0x18008dad0`
- end: `0x18008dc8d`
- name: `MF_ValidateArcDirection`
- size: `445`
- prototype: `__int64 __fastcall(HDC hdc)`
- caller_count: `3`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x1800202f4`
- `0x18008bd88`
- `0x18008d0d0`

## callees

- `0x180010140`
- `0x180021fa0`
- `0x180021fe0`
- `0x180022d1c`
- `0x1800710c4`
- `0x18008dad0`

## import_xrefs

- `GDI32!GdiGetEntry` at `0x18008dbad`
- `GDI32!GdiGetEntry` at `0x18008dbad`
- `GDI32!gW32PID` at `0x18008dbe1`
- `GDI32!gCookie` at `0x18008dbfd`
- `GDI32!gMaxGdiHandleCount` at `0x18008db88`
- `GDI32!pldcGet` at `0x18008dae0`
- `GDI32!pldcGet` at `0x18008dae0`
- `GDI32!GdiSetLastError` at `0x18008dc78`
- `GDI32!GdiSetLastError` at `0x18008dc78`
- `win32u!NtGdiUpdateTransform` at `0x18008dc2a`
- `win32u!NtGdiUpdateTransform` at `0x18008dc2a`

## pseudocode

```c
__int64 __fastcall MF_ValidateArcDirection(HDC hdc)
{
  __int64 v2; // rax
  __int64 v3; // rbp
  int v4; // r15d
  int DCDWord; // r14d
  int v6; // ebx
  int v7; // eax
  int v8; // eax
  int v9; // eax
  int v10; // eax
  int v11; // eax
  unsigned int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // rsi
  __int128 v16; // [rsp+20h] [rbp-58h] BYREF
  __int64 v17; // [rsp+30h] [rbp-48h]

  v2 = pldcGet(hdc);
  v3 = v2;
  if ( !v2 || ((unsigned int)hdc & 0x7F0000) == 0x660000 )
  {
    GdiSetLastError(6);
    return 0;
  }
  v4 = (*(_DWORD *)(v2 + 8) >> 13) & 1;
  DCDWord = GetDCDWord(hdc, 4);
  v6 = DCDWord == 2;
  if ( GetGraphicsMode(hdc) != 1 )
    goto LABEL_21;
  v7 = GetMapMode(hdc) - 2;
  if ( v7 )
  {
    v8 = v7 - 1;
    if ( v8 )
    {
      v9 = v8 - 1;
      if ( v9 )
      {
        v10 = v9 - 1;
        if ( v10 )
        {
          v11 = v10 - 1;
          if ( v11 )
          {
            if ( (unsigned int)(v11 - 1) > 1 )
              goto LABEL_21;
            v12 = HANDLE_TO_INDEX(hdc);
            if ( v12 >= gMaxGdiHandleCount )
              goto LABEL_21;
            v17 = 0;
            v16 = 0;
            if ( (int)GdiGetEntry(v12, &v16) < 0 )
              goto LABEL_21;
            if ( BYTE14(v16) != 1 )
              goto LABEL_21;
            if ( WORD6(v16) != WORD1(hdc) )
              goto LABEL_21;
            if ( (DWORD2(v16) & 0xFFFFFFFE) != gW32PID )
              goto LABEL_21;
            if ( !v17 )
              goto LABEL_21;
            v13 = __ROR8__(v17, 64 - (gCookie & 0x3Fu));
            v14 = v13 ^ gCookie;
            if ( v13 == gCookie )
              goto LABEL_21;
            if ( (*(_DWORD *)((v13 ^ gCookie) + 0x154) & 0xE000) == 0 || (unsigned int)NtGdiUpdateTransform(hdc) )
            {
              if ( ((*(_DWORD *)(v14 + 340) ^ (*(_DWORD *)(v14 + 340) >> 1)) & 0x100) == 0 )
                goto LABEL_21;
              goto LABEL_20;
            }
            return 0;
          }
        }
      }
    }
  }
LABEL_20:
  v6 = DCDWord != 2;
LABEL_21:
  if ( v4 == v6 )
    return 1;
  *(_DWORD *)(v3 + 8) ^= 0x2000u;
  return MF_SetD(hdc, (unsigned int)(v6 + 1), 57);
}

```

## disassembly

```asm
0x18008dad0  push    rbx
0x18008dad2  push    rbp
0x18008dad3  push    rsi
0x18008dad4  push    rdi
0x18008dad5  push    r14
0x18008dad7  push    r15
0x18008dad9  sub     rsp, 48h
0x18008dadd  mov     rdi, rcx
0x18008dae0  call    cs:__imp_pldcGet
0x18008dae6  mov     rbp, rax
0x18008dae9  test    rax, rax
0x18008daec  jz      loc_18008DC73
0x18008daf2  mov     edx, edi
0x18008daf4  and     edx, 7F0000h
0x18008dafa  cmp     edx, 660000h
0x18008db00  jz      loc_18008DC73
0x18008db06  mov     r15d, [rax+8]
0x18008db0a  xor     r8d, r8d
0x18008db0d  shr     r15d, 0Dh
0x18008db11  mov     rcx, rdi
0x18008db14  and     r15d, 1
0x18008db18  lea     edx, [r8+4]
0x18008db1c  call    GetDCDWord
0x18008db21  xor     ebx, ebx
0x18008db23  mov     rcx, rdi; hdc
0x18008db26  cmp     eax, 2
0x18008db29  mov     r14d, eax
0x18008db2c  setz    bl
0x18008db2f  call    GetGraphicsMode
0x18008db34  cmp     eax, 1
0x18008db37  jnz     loc_18008DC4F
0x18008db3d  mov     rcx, rdi; hdc
0x18008db40  call    GetMapMode
0x18008db45  sub     eax, 2
0x18008db48  jz      loc_18008DC46
0x18008db4e  sub     eax, 1
0x18008db51  jz      loc_18008DC46
0x18008db57  sub     eax, 1
0x18008db5a  jz      loc_18008DC46
0x18008db60  sub     eax, 1
0x18008db63  jz      loc_18008DC46
0x18008db69  sub     eax, 1
0x18008db6c  jz      loc_18008DC46
0x18008db72  sub     eax, 1
0x18008db75  jz      short loc_18008DB80
0x18008db77  cmp     eax, 1
0x18008db7a  jnz     loc_18008DC4F
0x18008db80  mov     rcx, rdi
0x18008db83  call    HANDLE_TO_INDEX
0x18008db88  mov     rcx, cs:__imp_gMaxGdiHandleCount
0x18008db8f  cmp     eax, [rcx]
0x18008db91  jnb     loc_18008DC4F
0x18008db97  xor     ecx, ecx
0x18008db99  lea     rdx, [rsp+78h+var_58]
0x18008db9e  mov     [rsp+78h+var_48], rcx
0x18008dba3  xorps   xmm0, xmm0
0x18008dba6  mov     ecx, eax
0x18008dba8  movups  [rsp+78h+var_58], xmm0
0x18008dbad  call    cs:__imp_GdiGetEntry
0x18008dbb3  test    eax, eax
0x18008dbb5  js      loc_18008DC4F
0x18008dbbb  cmp     byte ptr [rsp+78h+var_58+0Eh], 1
0x18008dbc0  jnz     loc_18008DC4F
0x18008dbc6  movzx   eax, byte ptr [rsp+78h+var_58+0Ch]
0x18008dbcb  movzx   ecx, byte ptr [rsp+78h+var_58+0Dh]
0x18008dbd0  shl     cx, 8
0x18008dbd4  or      cx, ax
0x18008dbd7  mov     eax, edi
0x18008dbd9  shr     eax, 10h
0x18008dbdc  cmp     cx, ax
0x18008dbdf  jnz     short loc_18008DC4F
0x18008dbe1  mov     rax, cs:__imp_gW32PID
0x18008dbe8  mov     ecx, dword ptr [rsp+78h+var_58+8]
0x18008dbec  and     ecx, 0FFFFFFFEh
0x18008dbef  cmp     ecx, [rax]
0x18008dbf1  jnz     short loc_18008DC4F
0x18008dbf3  mov     rdx, [rsp+78h+var_48]
0x18008dbf8  test    rdx, rdx
0x18008dbfb  jz      short loc_18008DC4F
0x18008dbfd  mov     rax, cs:__imp_gCookie
0x18008dc04  mov     ecx, 40h ; '@'
0x18008dc09  mov     rsi, [rax]
0x18008dc0c  mov     eax, esi
0x18008dc0e  and     eax, 3Fh
0x18008dc11  sub     ecx, eax
0x18008dc13  ror     rdx, cl
0x18008dc16  xor     rsi, rdx
0x18008dc19  jz      short loc_18008DC4F
0x18008dc1b  test    dword ptr [rsi+154h], 0E000h
0x18008dc25  jz      short loc_18008DC34
0x18008dc27  mov     rcx, rdi
0x18008dc2a  call    cs:__imp_NtGdiUpdateTransform
0x18008dc30  test    eax, eax
0x18008dc32  jz      short loc_18008DC7E
0x18008dc34  mov     eax, [rsi+154h]
0x18008dc3a  mov     ecx, eax
0x18008dc3c  shr     ecx, 1
0x18008dc3e  xor     ecx, eax
0x18008dc40  bt      ecx, 8
0x18008dc44  jnb     short loc_18008DC4F
0x18008dc46  xor     ebx, ebx
0x18008dc48  cmp     r14d, 2
0x18008dc4c  setnz   bl
0x18008dc4f  cmp     r15d, ebx
0x18008dc52  jnz     short loc_18008DC5B
0x18008dc54  mov     eax, 1
0x18008dc59  jmp     short loc_18008DC80
0x18008dc5b  btc     dword ptr [rbp+8], 0Dh
0x18008dc60  lea     edx, [rbx+1]
0x18008dc63  mov     r8d, 39h ; '9'
0x18008dc69  mov     rcx, rdi
0x18008dc6c  call    MF_SetD
0x18008dc71  jmp     short loc_18008DC80
0x18008dc73  mov     ecx, 6
0x18008dc78  call    cs:__imp_GdiSetLastError
0x18008dc7e  xor     eax, eax
0x18008dc80  add     rsp, 48h
0x18008dc84  pop     r15
0x18008dc86  pop     r14
0x18008dc88  pop     rdi
0x18008dc89  pop     rsi
0x18008dc8a  pop     rbp
0x18008dc8b  pop     rbx
0x18008dc8c  retn
```
