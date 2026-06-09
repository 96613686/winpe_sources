# CloneDirectoryPolicyObject

- ea: `0x1800366c4`
- end: `0x180036a8c`
- name: `CloneDirectoryPolicyObject`
- size: `968`
- prototype: `__int64 __fastcall(__int64, __int64 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x180035714`

## callees

- `0x180006f00`
- `0x18000c828`
- `0x18000e510`
- `0x180035a08`
- `0x180035d4c`
- `0x180036164`
- `0x18003657c`
- `0x1800366c4`
- `0x180036a94`
- `0x180036bd0`
- `0x180036c54`
- `0x180042e20`

## pseudocode

```c
__int64 __fastcall CloneDirectoryPolicyObject(__int64 a1, __int64 *a2)
{
  __int64 v4; // rax
  __int64 v5; // rsi
  unsigned int v6; // edi
  __int64 v7; // rcx
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // r9
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rcx
  unsigned __int16 *v14; // rcx
  __int64 v15; // rax
  unsigned __int16 *v16; // rcx
  __int64 v17; // rax
  __int64 v18; // rcx
  void *v19; // rcx
  __int64 v20; // rcx
  unsigned __int16 *v21; // rcx
  __int64 v22; // rax

  v4 = IpsecAllocMem(152);
  v5 = v4;
  if ( !v4 )
  {
    v6 = 14;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 82, WPP_536406ce45663b69fb8864445bd745b5_Traceguids, 14);
    goto LABEL_69;
  }
  v7 = *(_QWORD *)(a1 + 88);
  if ( v7 )
  {
    v6 = CloneDirectoryFilterObjects(v7, *(_DWORD *)(a1 + 80), (_QWORD *)(v4 + 88));
    if ( v6 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_68;
      v9 = 83;
      goto LABEL_10;
    }
    *(_DWORD *)(v5 + 80) = *(_DWORD *)(a1 + 80);
  }
  else
  {
    v6 = 0;
  }
  v11 = *(_QWORD *)(a1 + 104);
  if ( v11 )
  {
    v6 = CloneDirectoryNegPolObjects(v11, *(_DWORD *)(a1 + 96), (_QWORD *)(v5 + 104));
    if ( v6 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_68;
      v9 = 84;
      goto LABEL_10;
    }
    *(_DWORD *)(v5 + 96) = *(_DWORD *)(a1 + 96);
  }
  v12 = *(_QWORD *)(a1 + 72);
  if ( v12 )
  {
    v6 = CloneDirectoryNFAObjects(v12, *(_DWORD *)(a1 + 60), (_QWORD *)(v5 + 72));
    if ( v6 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_68;
      v9 = 85;
      goto LABEL_10;
    }
    *(_DWORD *)(v5 + 56) = *(_DWORD *)(a1 + 56);
    *(_DWORD *)(v5 + 60) = *(_DWORD *)(a1 + 60);
  }
  v13 = *(_QWORD *)(a1 + 120);
  if ( v13 )
  {
    v6 = CloneDirectoryISAKMPObjects(v13, *(_DWORD *)(a1 + 112), (_QWORD *)(v5 + 120));
    if ( v6 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_68;
      v9 = 86;
      goto LABEL_10;
    }
    *(_DWORD *)(v5 + 112) = *(_DWORD *)(a1 + 112);
  }
  if ( *(_QWORD *)a1 )
  {
    v6 = CopyDSToFQRegString(*(_QWORD *)a1, 0, v5);
    if ( v6 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_68;
      v9 = 87;
      goto LABEL_10;
    }
  }
  v14 = *(unsigned __int16 **)(a1 + 8);
  if ( v14 )
  {
    v15 = IpsecAllocStr(v14);
    *(_QWORD *)(v5 + 8) = v15;
    if ( !v15 )
    {
      v10 = 14;
      v6 = 14;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_68;
      v9 = 88;
      goto LABEL_67;
    }
  }
  v16 = *(unsigned __int16 **)(a1 + 16);
  if ( v16 )
  {
    v17 = IpsecAllocStr(v16);
    *(_QWORD *)(v5 + 16) = v17;
    if ( !v17 )
    {
      v10 = 14;
      v6 = 14;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_68;
      v9 = 89;
      goto LABEL_67;
    }
  }
  v18 = *(_QWORD *)(a1 + 48);
  if ( v18 )
  {
    v6 = CopyDSToFQRegString(v18, 1, v5 + 48);
    if ( v6 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_68;
      v9 = 90;
      goto LABEL_10;
    }
  }
  *(_DWORD *)(v5 + 24) = *(_DWORD *)(a1 + 24);
  v19 = *(void **)(a1 + 32);
  if ( v19 )
  {
    v6 = CopyBinaryValue(v19, *(unsigned int *)(a1 + 40));
    if ( v6 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_68;
      v9 = 91;
      goto LABEL_10;
    }
    *(_DWORD *)(v5 + 40) = *(_DWORD *)(a1 + 40);
  }
  v20 = *(_QWORD *)(a1 + 64);
  if ( !v20 || (v6 = CloneNFAReferencesDSToRegistry(v20, *(unsigned int *)(a1 + 56), v5 + 64, v5 + 56)) == 0 )
  {
    v21 = *(unsigned __int16 **)(a1 + 136);
    if ( !v21 || (v22 = IpsecAllocStr(v21), (*(_QWORD *)(v5 + 136) = v22) != 0) )
    {
      *(_DWORD *)(v5 + 128) = *(_DWORD *)(a1 + 128);
      *a2 = v5;
      return v6;
    }
    v10 = 14;
    v6 = 14;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_68;
    v9 = 93;
    goto LABEL_67;
  }
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
    goto LABEL_68;
  v9 = 92;
LABEL_10:
  v10 = v6;
LABEL_67:
  WPP_SF_d(v8[2], v9, WPP_536406ce45663b69fb8864445bd745b5_Traceguids, v10);
LABEL_68:
  FreeIpsecPolicyObject((LPVOID)v5);
LABEL_69:
  *a2 = 0;
  return v6;
}

```

## disassembly

```asm
0x1800366c4  push    rbx
0x1800366c6  push    rsi
0x1800366c7  push    rdi
0x1800366c8  push    r14
0x1800366ca  sub     rsp, 28h
0x1800366ce  mov     rbx, rcx
0x1800366d1  mov     r14, rdx
0x1800366d4  mov     ecx, 98h
0x1800366d9  call    IpsecAllocMem
0x1800366de  mov     rsi, rax
0x1800366e1  test    rax, rax
0x1800366e4  jnz     short loc_180036726
0x1800366e6  lea     r9d, [rax+0Eh]
0x1800366ea  mov     edi, r9d
0x1800366ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800366f4  lea     rax, WPP_GLOBAL_Control
0x1800366fb  cmp     rcx, rax
0x1800366fe  jz      loc_180036A68
0x180036704  test    byte ptr [rcx+1Ch], 10h
0x180036708  jz      loc_180036A68
0x18003670e  mov     rcx, [rcx+10h]
0x180036712  lea     edx, [rsi+52h]
0x180036715  lea     r8, WPP_536406ce45663b69fb8864445bd745b5_Traceguids
0x18003671c  call    WPP_SF_d
0x180036721  jmp     loc_180036A68
0x180036726  mov     rcx, [rbx+58h]
0x18003672a  test    rcx, rcx
0x18003672d  jz      short loc_180036777
0x18003672f  mov     edx, [rbx+50h]
0x180036732  lea     r8, [rax+58h]
0x180036736  call    CloneDirectoryFilterObjects
0x18003673b  mov     edi, eax
0x18003673d  test    eax, eax
0x18003673f  jz      short loc_18003676F
0x180036741  mov     rcx, cs:WPP_GLOBAL_Control
0x180036748  lea     rax, WPP_GLOBAL_Control
0x18003674f  cmp     rcx, rax
0x180036752  jz      loc_180036A60
0x180036758  test    byte ptr [rcx+1Ch], 10h
0x18003675c  jz      loc_180036A60
0x180036762  mov     edx, 53h ; 'S'
0x180036767  mov     r9d, edi
0x18003676a  jmp     loc_180036A50
0x18003676f  mov     eax, [rbx+50h]
0x180036772  mov     [rsi+50h], eax
0x180036775  jmp     short loc_180036779
0x180036777  xor     edi, edi
0x180036779  mov     rcx, [rbx+68h]
0x18003677d  test    rcx, rcx
0x180036780  jz      short loc_1800367C2
0x180036782  mov     edx, [rbx+60h]
0x180036785  lea     r8, [rsi+68h]
0x180036789  call    CloneDirectoryNegPolObjects
0x18003678e  mov     edi, eax
0x180036790  test    eax, eax
0x180036792  jz      short loc_1800367BC
0x180036794  mov     rcx, cs:WPP_GLOBAL_Control
0x18003679b  lea     rax, WPP_GLOBAL_Control
0x1800367a2  cmp     rcx, rax
0x1800367a5  jz      loc_180036A60
0x1800367ab  test    byte ptr [rcx+1Ch], 10h
0x1800367af  jz      loc_180036A60
0x1800367b5  mov     edx, 54h ; 'T'
0x1800367ba  jmp     short loc_180036767
0x1800367bc  mov     eax, [rbx+60h]
0x1800367bf  mov     [rsi+60h], eax
0x1800367c2  mov     rcx, [rbx+48h]
0x1800367c6  test    rcx, rcx
0x1800367c9  jz      short loc_180036814
0x1800367cb  mov     edx, [rbx+3Ch]
0x1800367ce  lea     r8, [rsi+48h]
0x1800367d2  call    CloneDirectoryNFAObjects
0x1800367d7  mov     edi, eax
0x1800367d9  test    eax, eax
0x1800367db  jz      short loc_180036808
0x1800367dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800367e4  lea     rax, WPP_GLOBAL_Control
0x1800367eb  cmp     rcx, rax
0x1800367ee  jz      loc_180036A60
0x1800367f4  test    byte ptr [rcx+1Ch], 10h
0x1800367f8  jz      loc_180036A60
0x1800367fe  mov     edx, 55h ; 'U'
0x180036803  jmp     loc_180036767
0x180036808  mov     eax, [rbx+38h]
0x18003680b  mov     [rsi+38h], eax
0x18003680e  mov     eax, [rbx+3Ch]
0x180036811  mov     [rsi+3Ch], eax
0x180036814  mov     rcx, [rbx+78h]
0x180036818  test    rcx, rcx
0x18003681b  jz      short loc_180036860
0x18003681d  mov     edx, [rbx+70h]
0x180036820  lea     r8, [rsi+78h]
0x180036824  call    CloneDirectoryISAKMPObjects
0x180036829  mov     edi, eax
0x18003682b  test    eax, eax
0x18003682d  jz      short loc_18003685A
0x18003682f  mov     rcx, cs:WPP_GLOBAL_Control
0x180036836  lea     rax, WPP_GLOBAL_Control
0x18003683d  cmp     rcx, rax
0x180036840  jz      loc_180036A60
0x180036846  test    byte ptr [rcx+1Ch], 10h
0x18003684a  jz      loc_180036A60
0x180036850  mov     edx, 56h ; 'V'
0x180036855  jmp     loc_180036767
0x18003685a  mov     eax, [rbx+70h]
0x18003685d  mov     [rsi+70h], eax
0x180036860  mov     rcx, [rbx]
0x180036863  test    rcx, rcx
0x180036866  jz      short loc_1800368A3
0x180036868  mov     r8, rsi
0x18003686b  xor     edx, edx
0x18003686d  call    CopyDSToFQRegString
0x180036872  mov     edi, eax
0x180036874  test    eax, eax
0x180036876  jz      short loc_1800368A3
0x180036878  mov     rcx, cs:WPP_GLOBAL_Control
0x18003687f  lea     rax, WPP_GLOBAL_Control
0x180036886  cmp     rcx, rax
0x180036889  jz      loc_180036A60
0x18003688f  test    byte ptr [rcx+1Ch], 10h
0x180036893  jz      loc_180036A60
0x180036899  mov     edx, 57h ; 'W'
0x18003689e  jmp     loc_180036767
0x1800368a3  mov     rcx, [rbx+8]; unsigned __int16 *
0x1800368a7  test    rcx, rcx
0x1800368aa  jz      short loc_1800368EB
0x1800368ac  call    IpsecAllocStr
0x1800368b1  mov     [rsi+8], rax
0x1800368b5  test    rax, rax
0x1800368b8  jnz     short loc_1800368EB
0x1800368ba  lea     r9d, [rax+0Eh]
0x1800368be  mov     edi, r9d
0x1800368c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800368c8  lea     rax, WPP_GLOBAL_Control
0x1800368cf  cmp     rcx, rax
0x1800368d2  jz      loc_180036A60
0x1800368d8  test    byte ptr [rcx+1Ch], 10h
0x1800368dc  jz      loc_180036A60
0x1800368e2  lea     edx, [r9+4Ah]
0x1800368e6  jmp     loc_180036A50
0x1800368eb  mov     rcx, [rbx+10h]; unsigned __int16 *
0x1800368ef  test    rcx, rcx
0x1800368f2  jz      short loc_180036933
0x1800368f4  call    IpsecAllocStr
0x1800368f9  mov     [rsi+10h], rax
0x1800368fd  test    rax, rax
0x180036900  jnz     short loc_180036933
0x180036902  lea     r9d, [rax+0Eh]
0x180036906  mov     edi, r9d
0x180036909  mov     rcx, cs:WPP_GLOBAL_Control
0x180036910  lea     rax, WPP_GLOBAL_Control
0x180036917  cmp     rcx, rax
0x18003691a  jz      loc_180036A60
0x180036920  test    byte ptr [rcx+1Ch], 10h
0x180036924  jz      loc_180036A60
0x18003692a  lea     edx, [r9+4Bh]
0x18003692e  jmp     loc_180036A50
0x180036933  mov     rcx, [rbx+30h]
0x180036937  test    rcx, rcx
0x18003693a  jz      short loc_18003697B
0x18003693c  lea     r8, [rsi+30h]
0x180036940  mov     edx, 1
0x180036945  call    CopyDSToFQRegString
0x18003694a  mov     edi, eax
0x18003694c  test    eax, eax
0x18003694e  jz      short loc_18003697B
0x180036950  mov     rcx, cs:WPP_GLOBAL_Control
0x180036957  lea     rax, WPP_GLOBAL_Control
0x18003695e  cmp     rcx, rax
0x180036961  jz      loc_180036A60
0x180036967  test    byte ptr [rcx+1Ch], 10h
0x18003696b  jz      loc_180036A60
0x180036971  mov     edx, 5Ah ; 'Z'
0x180036976  jmp     loc_180036767
0x18003697b  mov     eax, [rbx+18h]
0x18003697e  mov     [rsi+18h], eax
0x180036981  mov     rcx, [rbx+20h]; Src
0x180036985  test    rcx, rcx
0x180036988  jz      short loc_1800369CD
0x18003698a  mov     edx, [rbx+28h]; Size
0x18003698d  lea     r8, [rsi+20h]
0x180036991  call    CopyBinaryValue
0x180036996  mov     edi, eax
0x180036998  test    eax, eax
0x18003699a  jz      short loc_1800369C7
0x18003699c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800369a3  lea     rax, WPP_GLOBAL_Control
0x1800369aa  cmp     rcx, rax
0x1800369ad  jz      loc_180036A60
0x1800369b3  test    byte ptr [rcx+1Ch], 10h
0x1800369b7  jz      loc_180036A60
0x1800369bd  mov     edx, 5Bh ; '['
0x1800369c2  jmp     loc_180036767
0x1800369c7  mov     eax, [rbx+28h]
0x1800369ca  mov     [rsi+28h], eax
0x1800369cd  mov     rcx, [rbx+40h]
0x1800369d1  test    rcx, rcx
0x1800369d4  jz      short loc_180036A0F
0x1800369d6  mov     edx, [rbx+38h]
0x1800369d9  lea     r9, [rsi+38h]
0x1800369dd  lea     r8, [rsi+40h]
0x1800369e1  call    CloneNFAReferencesDSToRegistry
0x1800369e6  mov     edi, eax
0x1800369e8  test    eax, eax
0x1800369ea  jz      short loc_180036A0F
0x1800369ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800369f3  lea     rax, WPP_GLOBAL_Control
0x1800369fa  cmp     rcx, rax
0x1800369fd  jz      short loc_180036A60
0x1800369ff  test    byte ptr [rcx+1Ch], 10h
0x180036a03  jz      short loc_180036A60
0x180036a05  mov     edx, 5Ch ; '\'
0x180036a0a  jmp     loc_180036767
0x180036a0f  mov     rcx, [rbx+88h]; unsigned __int16 *
0x180036a16  test    rcx, rcx
0x180036a19  jz      short loc_180036A71
0x180036a1b  call    IpsecAllocStr
0x180036a20  mov     [rsi+88h], rax
0x180036a27  test    rax, rax
0x180036a2a  jnz     short loc_180036A71
0x180036a2c  lea     r9d, [rax+0Eh]
0x180036a30  mov     edi, r9d
0x180036a33  mov     rcx, cs:WPP_GLOBAL_Control
0x180036a3a  lea     rax, WPP_GLOBAL_Control
0x180036a41  cmp     rcx, rax
0x180036a44  jz      short loc_180036A60
0x180036a46  test    byte ptr [rcx+1Ch], 10h
0x180036a4a  jz      short loc_180036A60
0x180036a4c  lea     edx, [r9+4Fh]
0x180036a50  mov     rcx, [rcx+10h]
0x180036a54  lea     r8, WPP_536406ce45663b69fb8864445bd745b5_Traceguids
0x180036a5b  call    WPP_SF_d
0x180036a60  mov     rcx, rsi; lpMem
0x180036a63  call    FreeIpsecPolicyObject
0x180036a68  mov     qword ptr [r14], 0
0x180036a6f  jmp     short loc_180036A80
0x180036a71  mov     eax, [rbx+80h]
0x180036a77  mov     [rsi+80h], eax
0x180036a7d  mov     [r14], rsi
0x180036a80  mov     eax, edi
0x180036a82  add     rsp, 28h
0x180036a86  pop     r14
0x180036a88  pop     rdi
0x180036a89  pop     rsi
0x180036a8a  pop     rbx
0x180036a8b  retn
```
