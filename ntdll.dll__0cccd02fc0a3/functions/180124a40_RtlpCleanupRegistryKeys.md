# RtlpCleanupRegistryKeys

- ea: `0x180124a40`
- end: `0x180124e79`
- name: `RtlpCleanupRegistryKeys`
- size: `1081`
- prototype: ``
- caller_count: `0`
- callee_count: `23`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180009d60`
- `0x18000c7b0`
- `0x18000c9a0`
- `0x18000ede4`
- `0x18001861c`
- `0x18001b984`
- `0x180044e00`
- `0x1800535c0`
- `0x180053ab0`
- `0x180054eb0`
- `0x1800d97d0`
- `0x1800da090`
- `0x1800e8d1c`
- `0x180124a40`
- `0x180127d10`
- `0x1801435e8`
- `0x18015e4b0`
- `0x18015e910`
- `0x18015fe40`
- `0x180160280`
- `0x180160420`
- `0x180162000`
- `0x180163a80`

## string_xrefs

- `0x180124afb`: `\Registry\Machine\System\CurrentControlSet\Control\MUI\UILanguages`

## pseudocode

```c
__int64 RtlpCleanupRegistryKeys()
{
  unsigned int v0; // r13d
  __int64 Heap_0; // r15
  int SystemDefaultUILanguage; // ebx
  __int64 v3; // r11
  unsigned int v4; // eax
  __int64 v5; // rdi
  _QWORD *v6; // rsi
  int v7; // r14d
  unsigned __int64 v8; // rcx
  __int64 v9; // rcx
  _QWORD *v10; // rax
  _QWORD *v11; // rbx
  __int64 v12; // rcx
  void *v13; // rcx
  void *v14; // rcx
  int v16; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE Handle; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v18; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v19; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v20; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v21; // [rsp+60h] [rbp-A0h] BYREF
  HANDLE v22; // [rsp+68h] [rbp-98h] BYREF
  int v23; // [rsp+70h] [rbp-90h] BYREF
  __int64 v24; // [rsp+78h] [rbp-88h] BYREF
  _DWORD v25[2]; // [rsp+80h] [rbp-80h] BYREF
  wchar_t *String2; // [rsp+88h] [rbp-78h]
  char v27; // [rsp+90h] [rbp-70h] BYREF

  v0 = 0;
  Handle = 0;
  Heap_0 = 0;
  LOWORD(v16) = 0;
  v25[1] = 0;
  v20 = 0;
  LOWORD(v18) = 0;
  v21 = 0;
  v23 = 0;
  v22 = 0;
  NtIsUILanguageComitted();
  SystemDefaultUILanguage = RtlpCreateProcessRegistryInfo(&v21);
  if ( SystemDefaultUILanguage < 0 )
    goto LABEL_51;
  SystemDefaultUILanguage = RtlpGetSystemDefaultUILanguage(&v16, v21);
  if ( SystemDefaultUILanguage < 0 )
    goto LABEL_51;
  String2 = (wchar_t *)&v27;
  v25[0] = 11272192;
  if ( !(unsigned __int8)RtlLCIDToCultureName((unsigned __int16)v16, v25) || !v21 )
  {
    SystemDefaultUILanguage = -1073741823;
    goto LABEL_51;
  }
  v19 = 0;
  v20 = 0;
  SystemDefaultUILanguage = RtlStringLengthWorkerW_0(
                              L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\MUI\\UILanguages",
                              0x7FFF,
                              &v19);
  if ( SystemDefaultUILanguage < 0 )
  {
LABEL_51:
    if ( v22 )
      NtClose(v22);
    if ( Heap_0 )
      RtlFreeHeap_0(NtCurrentPeb()->ProcessHeap, 0, Heap_0);
  }
  else
  {
    *((_QWORD *)&v20 + 1) = v3;
    LOWORD(v20) = 2 * v19;
    WORD1(v20) = 2 * v19 + 2;
    SystemDefaultUILanguage = LdrpOpenKey(&v20, 0, 983103, &v22);
    if ( SystemDefaultUILanguage >= 0 )
    {
      Handle = 0;
      Heap_0 = RtlAllocateHeap_0(NtCurrentPeb()->ProcessHeap, 8, 512);
      if ( !Heap_0 )
      {
        SystemDefaultUILanguage = -1073741801;
        goto LABEL_51;
      }
      LOBYTE(v16) = 0;
      v4 = 0;
      LODWORD(v5) = 0;
      v6 = 0;
      while ( 1 )
      {
        LODWORD(v19) = v4;
        v7 = NtEnumerateKey(v22, v4, 0, Heap_0, 512, &v23, v16, Handle, v18);
        if ( v7 < 0 )
        {
LABEL_29:
          if ( Handle )
            NtClose(Handle);
          SystemDefaultUILanguage = 0;
          if ( v7 != -2147483622 )
            SystemDefaultUILanguage = v7;
          if ( v6 )
          {
            if ( (_DWORD)v5 )
            {
              if ( SystemDefaultUILanguage < 0 )
              {
                do
                {
                  v5 = (unsigned int)(v5 - 1);
                  v14 = (void *)v6[v5];
                  Handle = v14;
                  if ( v14 )
                    NtClose(v14);
                }
                while ( (_DWORD)v5 );
              }
              else
              {
                do
                {
                  v5 = (unsigned int)(v5 - 1);
                  v13 = (void *)v6[v5];
                  Handle = v13;
                  if ( v13 )
                  {
                    LOBYTE(v16) = 1;
                    NtDeleteKey(v13);
                    NtClose(Handle);
                  }
                }
                while ( (_DWORD)v5 );
              }
            }
            RtlFreeHeap_0(NtCurrentPeb()->ProcessHeap, 0, v6);
          }
          if ( SystemDefaultUILanguage >= 0 && (_BYTE)v16 )
          {
            ZwGetMUIRegistryInfo(2, 0, 0);
            RtlCleanUpTEBLangLists();
            RtlpInitMuiCriticalSection();
            RtlEnterCriticalSection(RegistryInfoCritSect);
            SystemDefaultUILanguage = RtlpMuiRegFreeRegistryInfo(g_RegInfo, 4095);
            if ( SystemDefaultUILanguage >= 0 )
            {
              if ( g_RegInfo )
                RtlFreeHeap_0(NtCurrentPeb()->ProcessHeap, 0, g_RegInfo);
              g_RegInfo = 0;
            }
            RtlLeaveCriticalSection(RegistryInfoCritSect);
          }
          goto LABEL_51;
        }
        v8 = *(unsigned int *)(Heap_0 + 12);
        if ( v8 + 24 <= 0x200 )
        {
          *(_WORD *)(Heap_0 + 2 * (v8 >> 1) + 16) = 0;
          if ( (int)RtlpMuiRegGetInstalledLanguageIndexByName(v21, Heap_0 + 16, 0, &v18) < 0 )
          {
            if ( wcsicmp((const wchar_t *)(Heap_0 + 16), String2) )
            {
              v20 = 0;
              if ( Heap_0 != -16 )
              {
                v24 = 0;
                if ( (int)RtlStringLengthWorkerW_0(Heap_0 + 16, 0x7FFF, &v24) < 0 )
                  goto LABEL_26;
                *((_QWORD *)&v20 + 1) = Heap_0 + 16;
                LOWORD(v20) = 2 * v24;
                WORD1(v20) = 2 * v24 + 2;
              }
              if ( (int)LdrpOpenKey(&v20, v22, 983103, &Handle) >= 0 )
              {
                if ( v6 )
                {
                  if ( (unsigned int)v5 >= v0 )
                  {
                    v10 = (_QWORD *)MuiRegAllocArray_0(v9, v0 + 10);
                    v11 = v10;
                    if ( !v10 )
                    {
                      v7 = -1073741801;
                      goto LABEL_29;
                    }
                    memmove(v10, v6, v0);
                    RtlFreeHeap_0(NtCurrentPeb()->ProcessHeap, 0, v6);
                    v0 += 10;
                    v6 = v11;
                  }
                }
                else
                {
                  v6 = (_QWORD *)MuiRegAllocArray_0(v9, 10);
                  if ( !v6 )
                  {
                    v7 = -1073741801;
                    goto LABEL_29;
                  }
                  v0 = 10;
                }
                v12 = (unsigned int)v5;
                LODWORD(v5) = v5 + 1;
                v6[v12] = Handle;
                Handle = 0;
              }
            }
          }
        }
LABEL_26:
        v4 = v19 + 1;
      }
    }
  }
  return (unsigned int)SystemDefaultUILanguage;
}

```

## disassembly

```asm
0x180124a40  push    rbp
0x180124a42  push    rbx
0x180124a43  push    rsi
0x180124a44  push    rdi
0x180124a45  push    r13
0x180124a47  push    r14
0x180124a49  push    r15
0x180124a4b  lea     rbp, [rsp-50h]
0x180124a50  sub     rsp, 150h
0x180124a57  mov     rax, cs:__security_cookie
0x180124a5e  xor     rax, rsp
0x180124a61  mov     [rbp+80h+var_40], rax
0x180124a65  xor     r13d, r13d
0x180124a68  xorps   xmm0, xmm0
0x180124a6b  mov     [rsp+180h+Handle], r13
0x180124a70  mov     r15d, r13d
0x180124a73  mov     word ptr [rsp+180h+var_150], r13w
0x180124a79  mov     [rbp+80h+var_FC], r13d
0x180124a7d  movups  [rsp+180h+var_130], xmm0
0x180124a82  mov     word ptr [rsp+180h+var_140], r13w
0x180124a88  mov     [rsp+180h+var_120], r13
0x180124a8d  mov     [rsp+180h+var_110], r13d
0x180124a92  mov     [rsp+180h+var_118], r13
0x180124a97  call    NtIsUILanguageComitted
0x180124a9c  lea     rcx, [rsp+180h+var_120]
0x180124aa1  call    RtlpCreateProcessRegistryInfo
0x180124aa6  mov     ebx, eax
0x180124aa8  test    eax, eax
0x180124aaa  js      loc_180124E2D
0x180124ab0  mov     rdx, [rsp+180h+var_120]
0x180124ab5  lea     rcx, [rsp+180h+var_150]
0x180124aba  call    RtlpGetSystemDefaultUILanguage
0x180124abf  mov     ebx, eax
0x180124ac1  test    eax, eax
0x180124ac3  js      loc_180124E2D
0x180124ac9  movzx   ecx, word ptr [rsp+180h+var_150]
0x180124ace  lea     rax, [rbp+80h+var_F0]
0x180124ad2  lea     rdx, [rbp+80h+var_100]
0x180124ad6  mov     [rbp+80h+String2], rax
0x180124ada  mov     [rbp+80h+var_100], 0AC0000h
0x180124ae1  call    RtlLCIDToCultureName
0x180124ae6  test    al, al
0x180124ae8  jnz     short loc_180124AF4
0x180124aea  mov     ebx, 0C0000001h
0x180124aef  jmp     loc_180124E2D
0x180124af4  cmp     [rsp+180h+var_120], r13
0x180124af9  jz      short loc_180124AEA
0x180124afb  lea     r11, aRegistryMachin_41; "\\Registry\\Machine\\System\\CurrentCon"...
0x180124b02  mov     [rsp+180h+var_138], r13
0x180124b07  xorps   xmm0, xmm0
0x180124b0a  lea     r8, [rsp+180h+var_138]
0x180124b0f  mov     rcx, r11
0x180124b12  mov     edx, 7FFFh
0x180124b17  movups  [rsp+180h+var_130], xmm0
0x180124b1c  call    RtlStringLengthWorkerW_0
0x180124b21  mov     ebx, eax
0x180124b23  test    eax, eax
0x180124b25  js      loc_180124E2D
0x180124b2b  movzx   eax, word ptr [rsp+180h+var_138]
0x180124b30  lea     r9, [rsp+180h+var_118]
0x180124b35  add     ax, ax
0x180124b38  mov     qword ptr [rsp+180h+var_130+8], r11
0x180124b3d  mov     word ptr [rsp+180h+var_130], ax
0x180124b42  lea     rcx, [rsp+180h+var_130]
0x180124b47  add     ax, 2
0x180124b4b  xor     edx, edx
0x180124b4d  mov     r8d, 0F003Fh
0x180124b53  mov     word ptr [rsp+180h+var_130+2], ax
0x180124b58  call    LdrpOpenKey
0x180124b5d  mov     ebx, eax
0x180124b5f  test    eax, eax
0x180124b61  js      loc_180124E58
0x180124b67  mov     [rsp+180h+Handle], r13
0x180124b6c  mov     edx, 8
0x180124b71  mov     rcx, gs:60h
0x180124b7a  mov     r8d, 200h
0x180124b80  mov     rcx, [rcx+30h]
0x180124b84  call    RtlAllocateHeap_0
0x180124b89  mov     r15, rax
0x180124b8c  test    rax, rax
0x180124b8f  jnz     short loc_180124B9B
0x180124b91  mov     ebx, 0C0000017h
0x180124b96  jmp     loc_180124E2D
0x180124b9b  mov     byte ptr [rsp+180h+var_150], r13b
0x180124ba0  mov     eax, r13d
0x180124ba3  mov     edi, r13d
0x180124ba6  mov     rsi, r13
0x180124ba9  lea     rcx, [rsp+180h+var_110]
0x180124bae  mov     dword ptr [rsp+180h+var_138], eax
0x180124bb2  mov     [rsp+180h+var_158], rcx
0x180124bb7  mov     r9, r15
0x180124bba  mov     rcx, [rsp+180h+var_118]
0x180124bbf  xor     r8d, r8d
0x180124bc2  mov     edx, eax
0x180124bc4  mov     [rsp+180h+var_160], 200h
0x180124bcc  call    NtEnumerateKey
0x180124bd1  mov     r14d, eax
0x180124bd4  test    eax, eax
0x180124bd6  js      loc_180124D2A
0x180124bdc  mov     ecx, [r15+0Ch]
0x180124be0  lea     rax, [rcx+18h]
0x180124be4  cmp     rax, 200h
0x180124bea  ja      loc_180124D11
0x180124bf0  shr     rcx, 1
0x180124bf3  lea     rbx, [r15+10h]
0x180124bf7  xor     eax, eax
0x180124bf9  lea     r9, [rsp+180h+var_140]
0x180124bfe  xor     r8d, r8d
0x180124c01  mov     rdx, rbx
0x180124c04  mov     [r15+rcx*2+10h], ax
0x180124c0a  mov     rcx, [rsp+180h+var_120]
0x180124c0f  call    RtlpMuiRegGetInstalledLanguageIndexByName
0x180124c14  test    eax, eax
0x180124c16  jns     loc_180124D11
0x180124c1c  mov     rdx, [rbp+80h+String2]; String2
0x180124c20  mov     rcx, rbx; String1
0x180124c23  call    _wcsicmp
0x180124c28  test    eax, eax
0x180124c2a  jz      loc_180124D11
0x180124c30  xorps   xmm0, xmm0
0x180124c33  movups  [rsp+180h+var_130], xmm0
0x180124c38  test    rbx, rbx
0x180124c3b  jz      short loc_180124C7B
0x180124c3d  lea     r8, [rsp+180h+var_108]
0x180124c42  mov     [rsp+180h+var_108], 0
0x180124c4b  mov     edx, 7FFFh
0x180124c50  mov     rcx, rbx
0x180124c53  call    RtlStringLengthWorkerW_0
0x180124c58  test    eax, eax
0x180124c5a  js      loc_180124D11
0x180124c60  movzx   eax, word ptr [rsp+180h+var_108]
0x180124c65  add     ax, ax
0x180124c68  mov     qword ptr [rsp+180h+var_130+8], rbx
0x180124c6d  mov     word ptr [rsp+180h+var_130], ax
0x180124c72  add     ax, 2
0x180124c76  mov     word ptr [rsp+180h+var_130+2], ax
0x180124c7b  mov     rdx, [rsp+180h+var_118]
0x180124c80  lea     r9, [rsp+180h+Handle]
0x180124c85  mov     r8d, 0F003Fh
0x180124c8b  lea     rcx, [rsp+180h+var_130]
0x180124c90  call    LdrpOpenKey
0x180124c95  test    eax, eax
0x180124c97  js      short loc_180124D11
0x180124c99  test    rsi, rsi
0x180124c9c  jnz     short loc_180124CB9
0x180124c9e  lea     edx, [rsi+0Ah]
0x180124ca1  call    _MuiRegAllocArray_0
0x180124ca6  xor     r13d, r13d
0x180124ca9  mov     rsi, rax
0x180124cac  test    rax, rax
0x180124caf  jz      short loc_180124D1C
0x180124cb1  mov     r13d, 0Ah
0x180124cb7  jmp     short loc_180124CFB
0x180124cb9  cmp     edi, r13d
0x180124cbc  jb      short loc_180124CFB
0x180124cbe  lea     edx, [r13+0Ah]
0x180124cc2  call    _MuiRegAllocArray_0
0x180124cc7  mov     rbx, rax
0x180124cca  test    rax, rax
0x180124ccd  jz      short loc_180124D24
0x180124ccf  mov     r8d, r13d; Size
0x180124cd2  mov     rdx, rsi; Src
0x180124cd5  mov     rcx, rax; void *
0x180124cd8  call    memmove
0x180124cdd  mov     rcx, gs:60h
0x180124ce6  mov     r8, rsi
0x180124ce9  xor     edx, edx
0x180124ceb  mov     rcx, [rcx+30h]
0x180124cef  call    RtlFreeHeap_0
0x180124cf4  add     r13d, 0Ah
0x180124cf8  mov     rsi, rbx
0x180124cfb  mov     rax, [rsp+180h+Handle]
0x180124d00  mov     ecx, edi
0x180124d02  inc     edi
0x180124d04  mov     [rsi+rcx*8], rax
0x180124d08  mov     [rsp+180h+Handle], 0
0x180124d11  mov     eax, dword ptr [rsp+180h+var_138]
0x180124d15  inc     eax
0x180124d17  jmp     loc_180124BA9
0x180124d1c  mov     r14d, 0C0000017h
0x180124d22  jmp     short loc_180124D2D
0x180124d24  mov     r14d, 0C0000017h
0x180124d2a  xor     r13d, r13d
0x180124d2d  mov     rcx, [rsp+180h+Handle]; Handle
0x180124d32  test    rcx, rcx
0x180124d35  jz      short loc_180124D3C
0x180124d37  call    NtClose
0x180124d3c  cmp     r14d, 8000001Ah
0x180124d43  mov     ebx, r13d
0x180124d46  cmovnz  ebx, r14d
0x180124d4a  test    rsi, rsi
0x180124d4d  jz      short loc_180124DB1
0x180124d4f  test    edi, edi
0x180124d51  jz      short loc_180124D9A
0x180124d53  test    ebx, ebx
0x180124d55  js      short loc_180124D81
0x180124d57  dec     edi
0x180124d59  mov     rcx, [rsi+rdi*8]
0x180124d5d  mov     [rsp+180h+Handle], rcx
0x180124d62  test    rcx, rcx
0x180124d65  jz      short loc_180124D7B
0x180124d67  mov     byte ptr [rsp+180h+var_150], 1
0x180124d6c  call    NtDeleteKey
0x180124d71  mov     rcx, [rsp+180h+Handle]; Handle
0x180124d76  call    NtClose
0x180124d7b  test    edi, edi
0x180124d7d  jnz     short loc_180124D57
0x180124d7f  jmp     short loc_180124D9A
0x180124d81  dec     edi
0x180124d83  mov     rcx, [rsi+rdi*8]; Handle
0x180124d87  mov     [rsp+180h+Handle], rcx
0x180124d8c  test    rcx, rcx
0x180124d8f  jz      short loc_180124D96
0x180124d91  call    NtClose
0x180124d96  test    edi, edi
0x180124d98  jnz     short loc_180124D81
0x180124d9a  mov     rcx, gs:60h
0x180124da3  mov     r8, rsi
0x180124da6  xor     edx, edx
0x180124da8  mov     rcx, [rcx+30h]
0x180124dac  call    RtlFreeHeap_0
0x180124db1  test    ebx, ebx
0x180124db3  js      short loc_180124E2D
0x180124db5  cmp     byte ptr [rsp+180h+var_150], r13b
0x180124dba  jz      short loc_180124E2D
0x180124dbc  xor     edx, edx
0x180124dbe  xor     r8d, r8d
0x180124dc1  lea     ecx, [rdx+2]
0x180124dc4  call    ZwGetMUIRegistryInfo
0x180124dc9  call    RtlCleanUpTEBLangLists
0x180124dce  call    RtlpInitMuiCriticalSection
0x180124dd3  lea     rcx, RegistryInfoCritSect
0x180124dda  call    RtlEnterCriticalSection
0x180124ddf  mov     rcx, cs:g_RegInfo
0x180124de6  mov     edx, 0FFFh
0x180124deb  call    RtlpMuiRegFreeRegistryInfo
0x180124df0  mov     ebx, eax
0x180124df2  test    eax, eax
0x180124df4  js      short loc_180124E21
0x180124df6  cmp     cs:g_RegInfo, r13
0x180124dfd  jz      short loc_180124E1A
0x180124dff  mov     rcx, gs:60h
0x180124e08  xor     edx, edx
0x180124e0a  mov     r8, cs:g_RegInfo
0x180124e11  mov     rcx, [rcx+30h]
0x180124e15  call    RtlFreeHeap_0
0x180124e1a  mov     cs:g_RegInfo, r13
0x180124e21  lea     rcx, RegistryInfoCritSect
0x180124e28  call    RtlLeaveCriticalSection
0x180124e2d  mov     rcx, [rsp+180h+var_118]; Handle
0x180124e32  test    rcx, rcx
0x180124e35  jz      short loc_180124E3C
0x180124e37  call    NtClose
0x180124e3c  test    r15, r15
0x180124e3f  jz      short loc_180124E58
0x180124e41  mov     rcx, gs:60h
0x180124e4a  mov     r8, r15
0x180124e4d  xor     edx, edx
0x180124e4f  mov     rcx, [rcx+30h]
0x180124e53  call    RtlFreeHeap_0
0x180124e58  mov     eax, ebx
0x180124e5a  mov     rcx, [rbp+80h+var_40]
0x180124e5e  xor     rcx, rsp; StackCookie
0x180124e61  call    __security_check_cookie
0x180124e66  add     rsp, 150h
0x180124e6d  pop     r15
0x180124e6f  pop     r14
0x180124e71  pop     r13
0x180124e73  pop     rdi
0x180124e74  pop     rsi
0x180124e75  pop     rbx
0x180124e76  pop     rbp
0x180124e77  retn
```
