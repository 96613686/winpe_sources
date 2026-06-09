# CreateServerMapView

- ea: `0x180005bd0`
- end: `0x180005d49`
- name: `CreateServerMapView`
- size: `377`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x18003e1d4`
- `0x18004b858`
- `0x18004bf54`

## callees

- `0x180005bd0`
- `0x180005d50`
- `0x180006eb0`
- `0x180046ec0`
- `0x180086b1c`
- `0x180086f78`

## import_xrefs

- `DNSAPI!NetInfo_Copy` at `0x180005c50`
- `DNSAPI!NetInfo_Copy` at `0x180005c50`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005cf2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005cf2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005c39`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005c39`

## pseudocode

```c
__int64 __fastcall CreateServerMapView(__int64 a1, _QWORD *a2)
{
  _QWORD *v2; // rdi
  HANDLE ProcessHeap; // rax
  _DWORD *v6; // rax
  __int64 v7; // rax
  unsigned int v8; // eax
  unsigned int v9; // ebx
  __int64 v11; // [rsp+30h] [rbp-18h] BYREF

  v2 = 0;
  v11 = 0;
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_qq(1035, 18, (unsigned int)WPP_cba5fe3efa5838b7033e5e8664507352_Traceguids, a1, (__int64)a2);
  if ( a2 && (*a2 = 0, a1) )
  {
    ProcessHeap = g_hProcessHeap;
    if ( !g_hProcessHeap )
    {
      ProcessHeap = GetProcessHeap();
      g_hProcessHeap = ProcessHeap;
    }
    v6 = HeapAlloc(ProcessHeap, 8u, 0x18u);
    v2 = v6;
    if ( v6 && (*v6 = 1, v7 = NetInfo_Copy(a1), (v2[2] = v7) != 0) )
    {
      v8 = CreateServerMap(a1, &v11);
      v9 = v8;
      if ( v8 )
      {
        if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
          WPP_SF_d(1035, 19, WPP_cba5fe3efa5838b7033e5e8664507352_Traceguids, v8);
      }
      else
      {
        v2[1] = v11;
        *a2 = v2;
        v2 = 0;
        v11 = 0;
      }
    }
    else
    {
      v9 = 14;
    }
  }
  else
  {
    v9 = 87;
  }
  DeRefServerMapView(v2);
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_d(1035, 20, WPP_cba5fe3efa5838b7033e5e8664507352_Traceguids, v9);
  return v9;
}

```

## disassembly

```asm
0x180005bd0  mov     [rsp+arg_10], rbx
0x180005bd5  mov     [rsp+arg_18], rsi
0x180005bda  push    rdi
0x180005bdb  sub     rsp, 40h
0x180005bdf  mov     rax, cs:__security_cookie
0x180005be6  xor     rax, rsp
0x180005be9  mov     [rsp+48h+var_10], rax
0x180005bee  xor     edi, edi
0x180005bf0  mov     rsi, rdx
0x180005bf3  mov     [rsp+48h+var_18], rdi
0x180005bf8  mov     rbx, rcx
0x180005bfb  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180005c02  jnz     loc_180005CCF
0x180005c08  test    rsi, rsi
0x180005c0b  jz      loc_180005CC8
0x180005c11  mov     [rsi], rdi
0x180005c14  test    rbx, rbx
0x180005c17  jz      loc_180005CC8
0x180005c1d  mov     rax, cs:g_hProcessHeap
0x180005c24  test    rax, rax
0x180005c27  jz      loc_180005CF2
0x180005c2d  mov     edx, 8; dwFlags
0x180005c32  mov     rcx, rax; hHeap
0x180005c35  lea     r8d, [rdx+10h]; dwBytes
0x180005c39  call    cs:__imp_HeapAlloc
0x180005c3f  mov     rdi, rax
0x180005c42  test    rax, rax
0x180005c45  jz      short loc_180005CC1
0x180005c47  mov     rcx, rbx
0x180005c4a  mov     dword ptr [rax], 1
0x180005c50  call    cs:__imp_NetInfo_Copy
0x180005c56  mov     [rdi+10h], rax
0x180005c5a  test    rax, rax
0x180005c5d  jz      short loc_180005CC1
0x180005c5f  lea     rdx, [rsp+48h+var_18]
0x180005c64  mov     rcx, rbx
0x180005c67  call    CreateServerMap
0x180005c6c  mov     ebx, eax
0x180005c6e  test    eax, eax
0x180005c70  jnz     loc_180005D04
0x180005c76  mov     rcx, [rsp+48h+var_18]
0x180005c7b  mov     [rdi+8], rcx
0x180005c7f  mov     [rsi], rdi
0x180005c82  xor     edi, edi
0x180005c84  mov     [rsp+48h+var_18], 0
0x180005c8d  mov     rcx, rdi; void *
0x180005c90  call    DeRefServerMapView
0x180005c95  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180005c9c  jnz     loc_180005D2B
0x180005ca2  mov     eax, ebx
0x180005ca4  mov     rcx, [rsp+48h+var_10]
0x180005ca9  xor     rcx, rsp; StackCookie
0x180005cac  call    __security_check_cookie
0x180005cb1  mov     rbx, [rsp+48h+arg_10]
0x180005cb6  mov     rsi, [rsp+48h+arg_18]
0x180005cbb  add     rsp, 40h
0x180005cbf  pop     rdi
0x180005cc0  retn
0x180005cc1  mov     ebx, 0Eh
0x180005cc6  jmp     short loc_180005C8D
0x180005cc8  mov     ebx, 57h ; 'W'
0x180005ccd  jmp     short loc_180005C8D
0x180005ccf  mov     edx, 12h
0x180005cd4  mov     [rsp+48h+var_28], rsi
0x180005cd9  mov     ecx, 40Bh
0x180005cde  lea     r8, WPP_cba5fe3efa5838b7033e5e8664507352_Traceguids
0x180005ce5  mov     r9, rbx
0x180005ce8  call    WPP_SF_qq
0x180005ced  jmp     loc_180005C08
0x180005cf2  call    cs:__imp_GetProcessHeap
0x180005cf8  mov     cs:g_hProcessHeap, rax
0x180005cff  jmp     loc_180005C2D
0x180005d04  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180005d0b  jz      short loc_180005C8D
0x180005d0d  mov     edx, 13h
0x180005d12  lea     r8, WPP_cba5fe3efa5838b7033e5e8664507352_Traceguids
0x180005d19  mov     ecx, 40Bh
0x180005d1e  mov     r9d, eax
0x180005d21  call    WPP_SF_d
0x180005d26  jmp     loc_180005C8D
0x180005d2b  mov     edx, 14h
0x180005d30  lea     r8, WPP_cba5fe3efa5838b7033e5e8664507352_Traceguids
0x180005d37  mov     ecx, 40Bh
0x180005d3c  mov     r9d, ebx
0x180005d3f  call    WPP_SF_d
0x180005d44  jmp     loc_180005CA2
```
