# MotionTurboJpeg::DecompressQuery(MotionTurboJpeg::INSTINFO *,MotionTurboJpeg::tagJPEGEXBMINFOHEADER const *,tagBITMAPINFOHEADER * const)

- ea: `0x180020e4c`
- end: `0x180020f50`
- name: `?DecompressQuery@MotionTurboJpeg@@YAKPEAUINSTINFO@1@PEBUtagJPEGEXBMINFOHEADER@1@QEAUtagBITMAPINFOHEADER@@@Z`
- size: `260`
- prototype: `__int64 __fastcall(MotionTurboJpeg *this, struct MotionTurboJpeg::INSTINFO *, const struct MotionTurboJpeg::tagJPEGEXBMINFOHEADER *, struct tagBITMAPINFOHEADER *const)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800205e0`

## callees

- `0x180020e4c`
- `0x180020f58`
- `0x180020fe0`
- `0x180024220`

## string_xrefs

- `0x180020f08`: `Decompress query: OTHER:%8x unsupported`
- `0x180020eee`: `Decompress query: non 1:1 unsupported`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall MotionTurboJpeg::DecompressQuery(
        MotionTurboJpeg *this,
        struct MotionTurboJpeg::INSTINFO *a2,
        const struct MotionTurboJpeg::tagJPEGEXBMINFOHEADER *a3,
        struct tagBITMAPINFOHEADER *const a4)
{
  unsigned int v4; // ecx
  unsigned int v5; // eax
  int v7; // r9d
  char *v8; // rcx
  char v9[256]; // [rsp+20h] [rbp-118h] BYREF

  if ( !a2 || *((_WORD *)a2 + 7) != 24 || *((_DWORD *)a2 + 4) != 1196444237 && *((_DWORD *)a2 + 4) != 1785750887 )
    return 4294967294LL;
  if ( *(_DWORD *)a2 == 68 && (*((_DWORD *)a2 + 12) || *((_DWORD *)a2 + 13) != 2 || *((_DWORD *)a2 + 14) != 8) )
    return 4294967294LL;
  v4 = *((_DWORD *)a2 + 1);
  if ( v4 > 0xFFDC )
    return 4294967294LL;
  v5 = *((_DWORD *)a2 + 2);
  if ( v5 > 0xFFDC )
    return 4294967294LL;
  if ( !a3 )
    return 0;
  v7 = *((_DWORD *)a3 + 4);
  if ( v7 == 844715353 )
  {
    if ( *((_WORD *)a3 + 7) == 16 )
      goto LABEL_15;
LABEL_23:
    if ( v7 != 1448433985 )
      goto LABEL_20;
    goto LABEL_19;
  }
  if ( v7 != 842094158 )
    goto LABEL_23;
LABEL_19:
  if ( *((_WORD *)a3 + 7) == 12 )
  {
LABEL_15:
    if ( *((_DWORD *)a3 + 1) == v4 && *((_DWORD *)a3 + 2) == v5 )
      return 0;
    v8 = "Decompress query: non 1:1 unsupported";
    goto LABEL_21;
  }
LABEL_20:
  StringCchPrintfA(v9, 0x100u, "Decompress query: OTHER:%8x unsupported", v7);
  v8 = v9;
LABEL_21:
  MotionTurboJpeg::LogErrorMessage((MotionTurboJpeg *)v8, (const char *)a2);
  return 4294967294LL;
}

```

## disassembly

```asm
0x180020e4c  sub     rsp, 138h
0x180020e53  mov     rax, cs:__security_cookie
0x180020e5a  xor     rax, rsp
0x180020e5d  mov     [rsp+138h+var_18], rax
0x180020e65  test    rdx, rdx
0x180020e68  jz      loc_180020F28
0x180020e6e  cmp     word ptr [rdx+0Eh], 18h
0x180020e73  jnz     loc_180020F28
0x180020e79  cmp     dword ptr [rdx+10h], 47504A4Dh
0x180020e80  jz      short loc_180020E8F
0x180020e82  cmp     dword ptr [rdx+10h], 6A706567h
0x180020e89  jnz     loc_180020F28
0x180020e8f  cmp     dword ptr [rdx], 44h ; 'D'
0x180020e92  jnz     short loc_180020EAE
0x180020e94  cmp     dword ptr [rdx+30h], 0
0x180020e98  jnz     loc_180020F28
0x180020e9e  cmp     dword ptr [rdx+34h], 2
0x180020ea2  jnz     loc_180020F28
0x180020ea8  cmp     dword ptr [rdx+38h], 8
0x180020eac  jnz     short loc_180020F28
0x180020eae  mov     ecx, [rdx+4]
0x180020eb1  mov     r9d, 0FFDCh
0x180020eb7  cmp     ecx, r9d
0x180020eba  ja      short loc_180020F28
0x180020ebc  mov     eax, [rdx+8]
0x180020ebf  cmp     eax, r9d
0x180020ec2  ja      short loc_180020F28
0x180020ec4  test    r8, r8
0x180020ec7  jnz     short loc_180020ECD
0x180020ec9  xor     eax, eax
0x180020ecb  jmp     short loc_180020F2D
0x180020ecd  mov     r9d, [r8+10h]
0x180020ed1  cmp     r9d, 32595559h
0x180020ed8  jnz     short loc_180020EF7
0x180020eda  cmp     word ptr [r8+0Eh], 10h
0x180020ee0  jnz     short loc_180020F45
0x180020ee2  cmp     [r8+4], ecx
0x180020ee6  jnz     short loc_180020EEE
0x180020ee8  cmp     [r8+8], eax
0x180020eec  jz      short loc_180020EC9
0x180020eee  lea     rcx, aDecompressQuer_0; "Decompress query: non 1:1 unsupported"
0x180020ef5  jmp     short loc_180020F23
0x180020ef7  cmp     r9d, 3231564Eh
0x180020efe  jnz     short loc_180020F45
0x180020f00  cmp     word ptr [r8+0Eh], 0Ch
0x180020f06  jz      short loc_180020EE2
0x180020f08  lea     r8, aDecompressQuer; "Decompress query: OTHER:%8x unsupported"
0x180020f0f  mov     edx, 100h; unsigned __int64
0x180020f14  lea     rcx, [rsp+138h+var_118]; char *
0x180020f19  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180020f1e  lea     rcx, [rsp+138h+var_118]; this
0x180020f23  call    ?LogErrorMessage@MotionTurboJpeg@@YAXPEBD@Z; MotionTurboJpeg::LogErrorMessage(char const *)
0x180020f28  mov     eax, 0FFFFFFFEh
0x180020f2d  mov     rcx, [rsp+138h+var_18]
0x180020f35  xor     rcx, rsp; StackCookie
0x180020f38  call    __security_check_cookie
0x180020f3d  add     rsp, 138h
0x180020f44  retn
0x180020f45  cmp     r9d, 56555941h
0x180020f4c  jnz     short loc_180020F08
0x180020f4e  jmp     short loc_180020F00
```
