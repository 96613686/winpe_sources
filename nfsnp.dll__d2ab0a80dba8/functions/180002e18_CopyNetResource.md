# CopyNetResource

- ea: `0x180002e18`
- end: `0x180002ff5`
- name: `CopyNetResource`
- size: `477`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180007fd0`

## callees

- `0x1800023f0`
- `0x180002e18`
- `0x180008ce0`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x180002fb9`
- `msvcrt!wcscpy_s` at `0x180002fb9`
- `KERNEL32!SetLastError` at `0x180002ecb`
- `KERNEL32!SetLastError` at `0x180002f79`
- `KERNEL32!SetLastError` at `0x180002ecb`
- `KERNEL32!SetLastError` at `0x180002f79`
- `KERNEL32!GlobalFree` at `0x180002f82`
- `KERNEL32!GlobalFree` at `0x180002f82`
- `KERNEL32!GlobalAlloc` at `0x180002e97`
- `KERNEL32!GlobalAlloc` at `0x180002f44`
- `KERNEL32!GlobalAlloc` at `0x180002e97`
- `KERNEL32!GlobalAlloc` at `0x180002f44`

## pseudocode

```c
_QWORD *__fastcall CopyNetResource(__int64 a1)
{
  _QWORD *v2; // rcx
  _QWORD *v3; // rax
  _QWORD *v4; // rbx
  __int64 v5; // rax
  __int64 v6; // rsi
  SIZE_T v7; // rdx
  rsize_t v8; // rsi
  wchar_t *v9; // rax

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
  if ( !a1 )
  {
    if ( v2 == &WPP_GLOBAL_Control )
      return 0;
    if ( (*((_BYTE *)v2 + 28) & 2) == 0 )
    {
LABEL_25:
      if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 2) != 0 )
        WPP_SF_(v2[2], 37, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids);
      return 0;
    }
    WPP_SF_(v2[2], 32, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids);
LABEL_24:
    v2 = WPP_GLOBAL_Control;
    goto LABEL_25;
  }
  v3 = GlobalAlloc(0x40u, 0x30u);
  v4 = v3;
  if ( !v3 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids);
    SetLastError(8u);
    goto LABEL_24;
  }
  *(_DWORD *)v3 = *(_DWORD *)a1;
  *((_DWORD *)v3 + 1) = *(_DWORD *)(a1 + 4);
  *((_DWORD *)v3 + 2) = *(_DWORD *)(a1 + 8);
  *((_DWORD *)v3 + 3) = *(_DWORD *)(a1 + 12);
  v3[2] = 0;
  v3[4] = 0;
  v3[5] = 0;
  v5 = *(_QWORD *)(a1 + 24);
  if ( v5 )
  {
    v6 = -1;
    do
      ++v6;
    while ( *(_WORD *)(v5 + 2 * v6) );
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids);
    v7 = 2LL * (unsigned int)(v6 + 1);
    v8 = (unsigned int)(v6 + 1);
    v9 = (wchar_t *)GlobalAlloc(0x40u, v7);
    v4[3] = v9;
    if ( !v9 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids);
      SetLastError(8u);
      GlobalFree(v4);
      goto LABEL_24;
    }
    wcscpy_s(v9, v8, *(const wchar_t **)(a1 + 24));
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids, v4);
  return v4;
}

```

## disassembly

```asm
0x180002e18  push    rbx
0x180002e1a  push    rbp
0x180002e1b  push    rsi
0x180002e1c  push    rdi
0x180002e1d  push    r14
0x180002e1f  push    r15
0x180002e21  sub     rsp, 28h
0x180002e25  mov     rdi, rcx
0x180002e28  mov     rcx, cs:WPP_GLOBAL_Control
0x180002e2f  lea     rbp, WPP_GLOBAL_Control
0x180002e36  lea     r14, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x180002e3d  cmp     rcx, rbp
0x180002e40  jz      short loc_180002E60
0x180002e42  test    byte ptr [rcx+1Ch], 1
0x180002e46  jz      short loc_180002E60
0x180002e48  mov     rcx, [rcx+10h]
0x180002e4c  mov     edx, 1Fh
0x180002e51  mov     r8, r14
0x180002e54  call    WPP_SF_
0x180002e59  mov     rcx, cs:WPP_GLOBAL_Control
0x180002e60  xor     r15d, r15d
0x180002e63  test    rdi, rdi
0x180002e66  jnz     short loc_180002E8F
0x180002e68  cmp     rcx, rbp
0x180002e6b  jz      loc_180002FAB
0x180002e71  test    byte ptr [rcx+1Ch], 2
0x180002e75  jz      loc_180002F8F
0x180002e7b  mov     rcx, [rcx+10h]
0x180002e7f  lea     edx, [rdi+20h]
0x180002e82  mov     r8, r14
0x180002e85  call    WPP_SF_
0x180002e8a  jmp     loc_180002F88
0x180002e8f  mov     edx, 30h ; '0'; dwBytes
0x180002e94  lea     ecx, [rdx+10h]; uFlags
0x180002e97  call    cs:__imp_GlobalAlloc
0x180002e9d  mov     rbx, rax
0x180002ea0  test    rax, rax
0x180002ea3  jnz     short loc_180002ED6
0x180002ea5  mov     rcx, cs:WPP_GLOBAL_Control
0x180002eac  cmp     rcx, rbp
0x180002eaf  jz      short loc_180002EC6
0x180002eb1  test    byte ptr [rcx+1Ch], 2
0x180002eb5  jz      short loc_180002EC6
0x180002eb7  mov     rcx, [rcx+10h]
0x180002ebb  lea     edx, [rax+21h]
0x180002ebe  mov     r8, r14
0x180002ec1  call    WPP_SF_
0x180002ec6  mov     ecx, 8; dwErrCode
0x180002ecb  call    cs:__imp_SetLastError
0x180002ed1  jmp     loc_180002F88
0x180002ed6  mov     eax, [rdi]
0x180002ed8  mov     [rbx], eax
0x180002eda  mov     eax, [rdi+4]
0x180002edd  mov     [rbx+4], eax
0x180002ee0  mov     eax, [rdi+8]
0x180002ee3  mov     [rbx+8], eax
0x180002ee6  mov     eax, [rdi+0Ch]
0x180002ee9  mov     [rbx+0Ch], eax
0x180002eec  mov     [rbx+10h], r15
0x180002ef0  mov     [rbx+20h], r15
0x180002ef4  mov     [rbx+28h], r15
0x180002ef8  mov     rax, [rdi+18h]
0x180002efc  test    rax, rax
0x180002eff  jz      loc_180002FBF
0x180002f05  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180002f09  inc     rsi
0x180002f0c  cmp     [rax+rsi*2], r15w
0x180002f11  jnz     short loc_180002F09
0x180002f13  mov     rcx, cs:WPP_GLOBAL_Control
0x180002f1a  cmp     rcx, rbp
0x180002f1d  jz      short loc_180002F36
0x180002f1f  test    byte ptr [rcx+1Ch], 8
0x180002f23  jz      short loc_180002F36
0x180002f25  mov     rcx, [rcx+10h]
0x180002f29  mov     edx, 22h ; '"'
0x180002f2e  mov     r8, r14
0x180002f31  call    WPP_SF_
0x180002f36  lea     eax, [rsi+1]
0x180002f39  mov     ecx, 40h ; '@'; uFlags
0x180002f3e  lea     rdx, [rax+rax]; dwBytes
0x180002f42  mov     esi, eax
0x180002f44  call    cs:__imp_GlobalAlloc
0x180002f4a  mov     [rbx+18h], rax
0x180002f4e  test    rax, rax
0x180002f51  jnz     short loc_180002FAF
0x180002f53  mov     rcx, cs:WPP_GLOBAL_Control
0x180002f5a  cmp     rcx, rbp
0x180002f5d  jz      short loc_180002F74
0x180002f5f  test    byte ptr [rcx+1Ch], 2
0x180002f63  jz      short loc_180002F74
0x180002f65  mov     rcx, [rcx+10h]
0x180002f69  lea     edx, [rax+23h]
0x180002f6c  mov     r8, r14
0x180002f6f  call    WPP_SF_
0x180002f74  mov     ecx, 8; dwErrCode
0x180002f79  call    cs:__imp_SetLastError
0x180002f7f  mov     rcx, rbx; hMem
0x180002f82  call    cs:__imp_GlobalFree
0x180002f88  mov     rcx, cs:WPP_GLOBAL_Control
0x180002f8f  cmp     rcx, rbp
0x180002f92  jz      short loc_180002FAB
0x180002f94  test    byte ptr [rcx+1Ch], 2
0x180002f98  jz      short loc_180002FAB
0x180002f9a  mov     rcx, [rcx+10h]
0x180002f9e  mov     edx, 25h ; '%'
0x180002fa3  mov     r8, r14
0x180002fa6  call    WPP_SF_
0x180002fab  xor     eax, eax
0x180002fad  jmp     short loc_180002FE8
0x180002faf  mov     r8, [rdi+18h]; Source
0x180002fb3  mov     rdx, rsi; SizeInWords
0x180002fb6  mov     rcx, rax; Destination
0x180002fb9  call    cs:__imp_wcscpy_s
0x180002fbf  mov     rcx, cs:WPP_GLOBAL_Control
0x180002fc6  cmp     rcx, rbp
0x180002fc9  jz      short loc_180002FE5
0x180002fcb  test    byte ptr [rcx+1Ch], 1
0x180002fcf  jz      short loc_180002FE5
0x180002fd1  mov     rcx, [rcx+10h]
0x180002fd5  mov     edx, 24h ; '$'
0x180002fda  mov     r9, rbx
0x180002fdd  mov     r8, r14
0x180002fe0  call    WPP_SF_q
0x180002fe5  mov     rax, rbx
0x180002fe8  add     rsp, 28h
0x180002fec  pop     r15
0x180002fee  pop     r14
0x180002ff0  pop     rdi
0x180002ff1  pop     rsi
0x180002ff2  pop     rbp
0x180002ff3  pop     rbx
0x180002ff4  retn
```
