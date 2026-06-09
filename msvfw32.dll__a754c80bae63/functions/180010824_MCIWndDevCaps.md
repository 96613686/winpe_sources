# MCIWndDevCaps

- ea: `0x180010824`
- end: `0x18001087e`
- name: `MCIWndDevCaps`
- size: `90`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180013edc`

## callees

- `0x1800014b0`
- `0x180010824`

## import_xrefs

- `WINMM!mciSendCommandW` at `0x18001085a`
- `WINMM!mciSendCommandW` at `0x18001085a`

## pseudocode

```c
__int64 __fastcall MCIWndDevCaps(__int64 a1, int a2)
{
  MCIDEVICEID v2; // ecx
  DWORD_PTR dwParam2[2]; // [rsp+20h] [rbp-28h] BYREF

  v2 = *(_DWORD *)(a1 + 20);
  *(_OWORD *)dwParam2 = 0;
  if ( !v2 )
    return 0;
  HIDWORD(dwParam2[1]) = a2;
  if ( mciSendCommandW(v2, 0x80Bu, 0x100u, (DWORD_PTR)dwParam2) )
    return 0;
  else
    return LODWORD(dwParam2[1]);
}

```

## disassembly

```asm
0x180010824  sub     rsp, 48h
0x180010828  mov     rax, cs:__security_cookie
0x18001082f  xor     rax, rsp
0x180010832  mov     [rsp+48h+var_18], rax
0x180010837  mov     ecx, [rcx+14h]; mciId
0x18001083a  xorps   xmm0, xmm0
0x18001083d  movups  xmmword ptr [rsp+48h+dwParam2], xmm0
0x180010842  test    ecx, ecx
0x180010844  jz      short loc_18001086A
0x180010846  mov     dword ptr [rsp+48h+dwParam2+0Ch], edx
0x18001084a  lea     r9, [rsp+48h+dwParam2]; dwParam2
0x18001084f  mov     edx, 80Bh; uMsg
0x180010854  mov     r8d, 100h; dwParam1
0x18001085a  call    cs:__imp_mciSendCommandW
0x180010860  test    eax, eax
0x180010862  jnz     short loc_18001086A
0x180010864  mov     eax, dword ptr [rsp+48h+dwParam2+8]
0x180010868  jmp     short loc_18001086C
0x18001086a  xor     eax, eax
0x18001086c  mov     rcx, [rsp+48h+var_18]
0x180010871  xor     rcx, rsp; StackCookie
0x180010874  call    __security_check_cookie
0x180010879  add     rsp, 48h
0x18001087d  retn
```
