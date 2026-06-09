# msOpenFile

- ea: `0x180002d90`
- end: `0x180002ea4`
- name: `msOpenFile`
- size: `276`
- prototype: `HMMIO __fastcall(LPWSTR pszFileName, LPMMCKINFO pmmcki, MMIOPROC *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180002a90`
- `0x180002eac`

## callees

- `0x180002d90`
- `0x180005fd5`
- `0x180005ff0`

## import_xrefs

- `WINMM!mmioOpenW` at `0x180002dfd`
- `WINMM!mmioOpenW` at `0x180002dfd`
- `WINMM!mmioDescend` at `0x180002e2a`
- `WINMM!mmioDescend` at `0x180002e43`
- `WINMM!mmioDescend` at `0x180002e2a`
- `WINMM!mmioDescend` at `0x180002e43`
- `WINMM!mmioSeek` at `0x180002e56`
- `WINMM!mmioSeek` at `0x180002e76`
- `WINMM!mmioSeek` at `0x180002e56`
- `WINMM!mmioSeek` at `0x180002e76`

## pseudocode

```c
HMMIO __fastcall msOpenFile(LPWSTR pszFileName, LPMMCKINFO pmmcki, MMIOPROC *a3)
{
  HMMIO result; // rax
  HMMIO v7; // rbx
  LONG v8; // eax
  _MMCKINFO pmmckia; // [rsp+20h] [rbp-A8h] BYREF
  _MMIOINFO pmmioinfo; // [rsp+40h] [rbp-88h] BYREF

  memset(&pmmckia, 0, sizeof(pmmckia));
  memset_0(&pmmioinfo, 0, sizeof(pmmioinfo));
  if ( a3 )
    pmmioinfo.pIOProc = a3;
  else
    pmmioinfo.fccIOProc = 542330692;
  result = mmioOpenW(pszFileName, &pmmioinfo, 0x20u);
  v7 = result;
  if ( result )
  {
    pmmckia.fccType = 1145654610;
    pmmcki->ckid = 1635017060;
    if ( mmioDescend(result, &pmmckia, 0, 0x20u) || mmioDescend(v7, pmmcki, &pmmckia, 0x10u) )
    {
      v8 = mmioSeek(v7, 0, 2);
      *(_QWORD *)&pmmcki->fccType = 0;
      pmmcki->cksize = v8;
      pmmcki->dwFlags = 0;
      mmioSeek(v7, 0, 0);
    }
    return v7;
  }
  return result;
}

```

## disassembly

```asm
0x180002d90  mov     [rsp+arg_10], rbx
0x180002d95  mov     [rsp+arg_18], rsi
0x180002d9a  push    rdi
0x180002d9b  sub     rsp, 0C0h
0x180002da2  mov     rax, cs:__security_cookie
0x180002da9  xor     rax, rsp
0x180002dac  mov     [rsp+0C8h+var_18], rax
0x180002db4  xor     eax, eax
0x180002db6  mov     rbx, r8
0x180002db9  mov     rdi, rdx
0x180002dbc  mov     [rsp+0C8h+pmmcki.dwFlags], eax
0x180002dc0  mov     rsi, rcx
0x180002dc3  xorps   xmm0, xmm0
0x180002dc6  xor     edx, edx; Val
0x180002dc8  lea     rcx, [rsp+0C8h+pmmioinfo]; void *
0x180002dcd  lea     r8d, [rax+64h]; Size
0x180002dd1  movups  xmmword ptr [rsp+0C8h+pmmcki.ckid], xmm0
0x180002dd6  call    memset_0
0x180002ddb  test    rbx, rbx
0x180002dde  jz      short loc_180002DE7
0x180002de0  mov     [rsp+0C8h+pmmioinfo.pIOProc], rbx
0x180002de5  jmp     short loc_180002DEF
0x180002de7  mov     [rsp+0C8h+pmmioinfo.fccIOProc], 20534F44h
0x180002def  mov     r8d, 20h ; ' '; fdwOpen
0x180002df5  lea     rdx, [rsp+0C8h+pmmioinfo]; pmmioinfo
0x180002dfa  mov     rcx, rsi; pszFileName
0x180002dfd  call    cs:__imp_mmioOpenW
0x180002e03  mov     rbx, rax
0x180002e06  test    rax, rax
0x180002e09  jz      short loc_180002E7F
0x180002e0b  mov     r9d, 20h ; ' '; fuDescend
0x180002e11  mov     [rsp+0C8h+pmmcki.fccType], 44494D52h
0x180002e19  xor     r8d, r8d; pmmckiParent
0x180002e1c  mov     dword ptr [rdi], 61746164h
0x180002e22  lea     rdx, [rsp+0C8h+pmmcki]; pmmcki
0x180002e27  mov     rcx, rbx; hmmio
0x180002e2a  call    cs:__imp_mmioDescend
0x180002e30  test    eax, eax
0x180002e32  jnz     short loc_180002E4D
0x180002e34  lea     r9d, [rax+10h]; fuDescend
0x180002e38  mov     rdx, rdi; pmmcki
0x180002e3b  lea     r8, [rsp+0C8h+pmmcki]; pmmckiParent
0x180002e40  mov     rcx, rbx; hmmio
0x180002e43  call    cs:__imp_mmioDescend
0x180002e49  test    eax, eax
0x180002e4b  jz      short loc_180002E7C
0x180002e4d  xor     edx, edx; lOffset
0x180002e4f  mov     rcx, rbx; hmmio
0x180002e52  lea     r8d, [rdx+2]; iOrigin
0x180002e56  call    cs:__imp_mmioSeek
0x180002e5c  xor     r8d, r8d; iOrigin
0x180002e5f  mov     qword ptr [rdi+8], 0
0x180002e67  xor     edx, edx; lOffset
0x180002e69  mov     [rdi+4], eax
0x180002e6c  mov     rcx, rbx; hmmio
0x180002e6f  mov     dword ptr [rdi+10h], 0
0x180002e76  call    cs:__imp_mmioSeek
0x180002e7c  mov     rax, rbx
0x180002e7f  mov     rcx, [rsp+0C8h+var_18]
0x180002e87  xor     rcx, rsp; StackCookie
0x180002e8a  call    __security_check_cookie
0x180002e8f  lea     r11, [rsp+0C8h+var_8]
0x180002e97  mov     rbx, [r11+20h]
0x180002e9b  mov     rsi, [r11+28h]
0x180002e9f  mov     rsp, r11
0x180002ea2  pop     rdi
0x180002ea3  retn
```
