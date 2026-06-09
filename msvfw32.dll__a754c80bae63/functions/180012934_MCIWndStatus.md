# MCIWndStatus

- ea: `0x180012934`
- end: `0x180012999`
- name: `MCIWndStatus`
- size: `101`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000fe2c`
- `0x180010cc0`
- `0x18001494c`

## callees

- `0x1800014b0`
- `0x180012934`

## import_xrefs

- `WINMM!mciSendCommandW` at `0x180012976`
- `WINMM!mciSendCommandW` at `0x180012976`

## pseudocode

```c
__int64 __fastcall MCIWndStatus(__int64 a1, int a2, unsigned int a3)
{
  MCIDEVICEID v3; // ecx
  bool v5; // zf
  __int64 result; // rax
  DWORD_PTR dwParam2[2]; // [rsp+20h] [rbp-28h] BYREF
  __int64 v8; // [rsp+30h] [rbp-18h]

  v3 = *(_DWORD *)(a1 + 20);
  v8 = 0;
  *(_OWORD *)dwParam2 = 0;
  if ( !v3 )
    return a3;
  LODWORD(v8) = a2;
  v5 = mciSendCommandW(v3, 0x814u, 0x100u, (DWORD_PTR)dwParam2) == 0;
  result = LODWORD(dwParam2[1]);
  if ( !v5 )
    return a3;
  return result;
}

```

## disassembly

```asm
0x180012934  push    rbx
0x180012936  sub     rsp, 40h
0x18001293a  mov     rax, cs:__security_cookie
0x180012941  xor     rax, rsp
0x180012944  mov     [rsp+48h+var_10], rax
0x180012949  mov     ecx, [rcx+14h]; mciId
0x18001294c  xor     eax, eax
0x18001294e  mov     [rsp+48h+var_18], rax
0x180012953  xorps   xmm0, xmm0
0x180012956  mov     ebx, r8d
0x180012959  movups  xmmword ptr [rsp+48h+dwParam2], xmm0
0x18001295e  test    ecx, ecx
0x180012960  jz      short loc_180012984
0x180012962  mov     dword ptr [rsp+48h+var_18], edx
0x180012966  lea     r9, [rsp+48h+dwParam2]; dwParam2
0x18001296b  mov     edx, 814h; uMsg
0x180012970  mov     r8d, 100h; dwParam1
0x180012976  call    cs:__imp_mciSendCommandW
0x18001297c  test    eax, eax
0x18001297e  mov     eax, dword ptr [rsp+48h+dwParam2+8]
0x180012982  jz      short loc_180012986
0x180012984  mov     eax, ebx
0x180012986  mov     rcx, [rsp+48h+var_10]
0x18001298b  xor     rcx, rsp; StackCookie
0x18001298e  call    __security_check_cookie
0x180012993  add     rsp, 40h
0x180012997  pop     rbx
0x180012998  retn
```
