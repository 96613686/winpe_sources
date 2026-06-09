# sub_1401BF7EE

- ea: `0x1401bf7ee`
- end: `0x1401bf918`
- name: `sub_1401BF7EE`
- size: `298`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1401bf686`

## callees

- `0x1400b4d60`
- `0x1400c67e0`
- `0x1400dfee0`
- `0x14011fa70`
- `0x140152ce0`
- `0x1401bf7ee`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1401ba17d`
- `KERNEL32!GetLastError` at `0x1401ba18f`
- `KERNEL32!GetLastError` at `0x1401bf8c2`
- `KERNEL32!GetLastError` at `0x1401ba17d`
- `KERNEL32!GetLastError` at `0x1401ba18f`
- `KERNEL32!GetLastError` at `0x1401bf8c2`
- `USER32!CreateWindowStationW` at `0x1401ba1ae`
- `USER32!CreateWindowStationW` at `0x1401bf8ad`
- `USER32!CreateWindowStationW` at `0x1401ba1ae`
- `USER32!CreateWindowStationW` at `0x1401bf8ad`
- `USER32!GetProcessWindowStation` at `0x1401bf81c`
- `USER32!GetProcessWindowStation` at `0x1401bf81c`

## pseudocode

```c
__int64 __fastcall sub_1401BF7EE(__int64 a1, HWINSTA *a2)
{
  HWINSTA v2; // rax
  HWINSTA ProcessWindowStation; // rax
  HWINSTA v6; // rbx
  int v7; // r15d
  HWINSTA v8; // rax
  __int64 v10; // [rsp+0h] [rbp-138h] BYREF
  struct _SECURITY_ATTRIBUTES sa; // [rsp+20h] [rbp-118h] BYREF
  _BYTE v12[32]; // [rsp+40h] [rbp-F8h] BYREF
  __int64 v13; // [rsp+60h] [rbp-D8h]
  _BYTE Dst[136]; // [rsp+70h] [rbp-C8h] BYREF
  __int64 v15; // [rsp+F8h] [rbp-40h]

  ProcessWindowStation = GetProcessWindowStation();
  if ( !ProcessWindowStation )
  {
    *(_DWORD *)a1 = 34;
    *(_DWORD *)(a1 + 4) = GetLastError();
    *(_BYTE *)(a1 + 8) = 0;
    goto LABEL_7;
  }
  v6 = ProcessWindowStation;
  v7 = 0;
  memset(Dst, 0, sizeof(Dst));
  sub_1400B4D60(Dst, v6, 2, 4);
  if ( !Dst[128] )
    goto LABEL_9;
  memset(v12, 0, sizeof(v12));
  v13 = 0;
  sub_1400C67E0(Dst, v12);
  *(&sa.nLength + 1) = 0;
  *(_QWORD *)&sa.bInheritHandle = 0;
  sa.nLength = 24;
  sa.lpSecurityDescriptor = v12;
  v8 = CreateWindowStationW(0, 0, 0x80000008, &sa);
  *a2 = v8;
  if ( !v8 )
  {
    if ( GetLastError() == 5 )
    {
      v2 = CreateWindowStationW(0, 0, 0xAu, &sa);
      *a2 = v2;
    }
    else
    {
      v2 = *a2;
    }
    v7 = 12;
    if ( v2 )
      v7 = 0;
  }
  for ( *(_DWORD *)a1 = v7; ; *(_DWORD *)a1 = 35 )
  {
    *(_DWORD *)(a1 + 4) = GetLastError();
    *(_BYTE *)(a1 + 8) = 0;
    if ( Dst[128] == 1 )
      sub_1400DFEE0(Dst);
LABEL_7:
    if ( _security_cookie == ((unsigned __int64)&v10 ^ v15) )
      break;
LABEL_9:
    ;
  }
  return a1;
}

```

## disassembly

```asm
0x1401bf7ee  push    r15
0x1401bf7f0  push    r14
0x1401bf7f2  push    rsi
0x1401bf7f3  push    rdi
0x1401bf7f4  push    rbx
0x1401bf7f5  sub     rsp, 110h
0x1401bf7fc  movaps  [rsp+138h+var_38], xmm6
0x1401bf804  mov     rdi, rdx
0x1401bf807  mov     rsi, rcx
0x1401bf80a  mov     rax, cs:__security_cookie
0x1401bf811  xor     rax, rsp
0x1401bf814  mov     [rsp+138h+var_40], rax
0x1401bf81c  call    cs:GetProcessWindowStation
0x1401bf822  test    rax, rax
0x1401bf825  jz      loc_1401BA177
0x1401bf82b  mov     rbx, rax
0x1401bf82e  xor     r15d, r15d
0x1401bf831  lea     r14, [rsp+138h+Dst]
0x1401bf836  mov     r8d, 88h; Size
0x1401bf83c  mov     rcx, r14; Dst
0x1401bf83f  xor     edx, edx; Val
0x1401bf841  call    memset
0x1401bf846  mov     rcx, r14
0x1401bf849  mov     rdx, rbx
0x1401bf84c  mov     r8d, 2
0x1401bf852  mov     r9d, 4
0x1401bf858  call    sub_1400B4D60
0x1401bf85d  cmp     byte ptr [r14+80h], 0
0x1401bf865  jz      loc_1401BA16C
0x1401bf86b  xorps   xmm6, xmm6
0x1401bf86e  lea     rbx, [rsp+138h+var_F8]
0x1401bf873  movaps  xmmword ptr [rbx+10h], xmm6
0x1401bf877  movaps  xmmword ptr [rbx], xmm6
0x1401bf87a  mov     [rbx+20h], r15
0x1401bf87e  lea     rcx, [rsp+138h+Dst]
0x1401bf883  mov     rdx, rbx
0x1401bf886  call    sub_1400C67E0
0x1401bf88b  lea     r9, [rsp+138h+sa]; lpsa
0x1401bf890  movaps  xmmword ptr [r9], xmm6
0x1401bf894  mov     [r9+10h], r15
0x1401bf898  mov     dword ptr [r9], 18h
0x1401bf89f  mov     [r9+8], rbx
0x1401bf8a3  xor     ecx, ecx; lpwinsta
0x1401bf8a5  xor     edx, edx; dwFlags
0x1401bf8a7  mov     r8d, 80000008h; dwDesiredAccess
0x1401bf8ad  call    cs:CreateWindowStationW
0x1401bf8b3  mov     [rdi], rax
0x1401bf8b6  test    rax, rax
0x1401bf8b9  jz      loc_1401BA18F
0x1401bf8bf  mov     [rsi], r15d
0x1401bf8c2  call    cs:__imp_GetLastError
0x1401bf8c8  mov     [rsi+4], eax
0x1401bf8cb  mov     byte ptr [rsi+8], 0
0x1401bf8cf  cmp     [rsp+138h+var_48], 1
0x1401bf8d7  jnz     short loc_1401BF8E3
0x1401bf8d9  lea     rcx, [rsp+138h+Dst]
0x1401bf8de  call    sub_1400DFEE0
0x1401bf8e3  mov     rax, [rsp+138h+var_40]
0x1401bf8eb  xor     rax, rsp
0x1401bf8ee  mov     rcx, cs:__security_cookie
0x1401bf8f5  cmp     rcx, rax
0x1401bf8f8  jnz     loc_1401BA15C
0x1401bf8fe  mov     rax, rsi
0x1401bf901  movaps  xmm6, [rsp+138h+var_38]
0x1401bf909  add     rsp, 110h
0x1401bf910  pop     rbx
0x1401bf911  pop     rdi
0x1401bf912  pop     rsi
0x1401bf913  pop     r14
0x1401bf915  pop     r15
0x1401bf917  retn
0x1401ba15c  mov     rcx, [rsp+138h+var_40]
0x1401ba164  xor     rcx, rsp; StackCookie
0x1401ba167  call    __security_check_cookie
0x1401ba16c  mov     dword ptr [rsi], 23h ; '#'
0x1401ba172  jmp     loc_1401BF8C2
0x1401ba177  mov     dword ptr [rsi], 22h ; '"'
0x1401ba17d  call    cs:__imp_GetLastError
0x1401ba183  mov     [rsi+4], eax
0x1401ba186  mov     byte ptr [rsi+8], 0
0x1401ba18a  jmp     loc_1401BF8E3
0x1401ba18f  call    cs:__imp_GetLastError
0x1401ba195  cmp     eax, 5
0x1401ba198  jz      short loc_1401BA19F
0x1401ba19a  mov     rax, [rdi]
0x1401ba19d  jmp     short loc_1401BA1B7
0x1401ba19f  lea     r9, [rsp+138h+sa]; lpsa
0x1401ba1a4  xor     ecx, ecx; lpwinsta
0x1401ba1a6  xor     edx, edx; dwFlags
0x1401ba1a8  mov     r8d, 0Ah; dwDesiredAccess
0x1401ba1ae  call    cs:CreateWindowStationW
0x1401ba1b4  mov     [rdi], rax
0x1401ba1b7  xor     ecx, ecx
0x1401ba1b9  test    rax, rax
0x1401ba1bc  mov     r15d, 0Ch
0x1401ba1c2  cmovnz  r15d, ecx
0x1401ba1c6  jmp     loc_1401BF8BF
```
