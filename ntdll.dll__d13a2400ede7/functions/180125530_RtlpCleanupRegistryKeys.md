# RtlpCleanupRegistryKeys

- ea: `0x180125530`
- end: `0x180125969`
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
- `0x180061a00`
- `0x18006ffa0`
- `0x180070490`
- `0x180071890`
- `0x1800da250`
- `0x1800dab10`
- `0x1800e937c`
- `0x180125530`
- `0x180128800`
- `0x180143f78`
- `0x18015ecc0`
- `0x18015f120`
- `0x180160650`
- `0x180160a90`
- `0x180160c30`
- `0x180162810`
- `0x180164280`

## string_xrefs

- `0x1801255eb`: `\Registry\Machine\System\CurrentControlSet\Control\MUI\UILanguages`

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
0x180125530  push    rbp
0x180125532  push    rbx
0x180125533  push    rsi
0x180125534  push    rdi
0x180125535  push    r13
0x180125537  push    r14
0x180125539  push    r15
0x18012553b  lea     rbp, [rsp-50h]
0x180125540  sub     rsp, 150h
0x180125547  mov     rax, cs:__security_cookie
0x18012554e  xor     rax, rsp
0x180125551  mov     [rbp+80h+var_40], rax
0x180125555  xor     r13d, r13d
0x180125558  xorps   xmm0, xmm0
0x18012555b  mov     [rsp+180h+Handle], r13
0x180125560  mov     r15d, r13d
0x180125563  mov     word ptr [rsp+180h+var_150], r13w
0x180125569  mov     [rbp+80h+var_FC], r13d
0x18012556d  movups  [rsp+180h+var_130], xmm0
0x180125572  mov     word ptr [rsp+180h+var_140], r13w
0x180125578  mov     [rsp+180h+var_120], r13
0x18012557d  mov     [rsp+180h+var_110], r13d
0x180125582  mov     [rsp+180h+var_118], r13
0x180125587  call    NtIsUILanguageComitted
0x18012558c  lea     rcx, [rsp+180h+var_120]
0x180125591  call    RtlpCreateProcessRegistryInfo
0x180125596  mov     ebx, eax
0x180125598  test    eax, eax
0x18012559a  js      loc_18012591D
0x1801255a0  mov     rdx, [rsp+180h+var_120]
0x1801255a5  lea     rcx, [rsp+180h+var_150]
0x1801255aa  call    RtlpGetSystemDefaultUILanguage
0x1801255af  mov     ebx, eax
0x1801255b1  test    eax, eax
0x1801255b3  js      loc_18012591D
0x1801255b9  movzx   ecx, word ptr [rsp+180h+var_150]
0x1801255be  lea     rax, [rbp+80h+var_F0]
0x1801255c2  lea     rdx, [rbp+80h+var_100]
0x1801255c6  mov     [rbp+80h+String2], rax
0x1801255ca  mov     [rbp+80h+var_100], 0AC0000h
0x1801255d1  call    RtlLCIDToCultureName
0x1801255d6  test    al, al
0x1801255d8  jnz     short loc_1801255E4
0x1801255da  mov     ebx, 0C0000001h
0x1801255df  jmp     loc_18012591D
0x1801255e4  cmp     [rsp+180h+var_120], r13
0x1801255e9  jz      short loc_1801255DA
0x1801255eb  lea     r11, aRegistryMachin_41; "\\Registry\\Machine\\System\\CurrentCon"...
0x1801255f2  mov     [rsp+180h+var_138], r13
0x1801255f7  xorps   xmm0, xmm0
0x1801255fa  lea     r8, [rsp+180h+var_138]
0x1801255ff  mov     rcx, r11
0x180125602  mov     edx, 7FFFh
0x180125607  movups  [rsp+180h+var_130], xmm0
0x18012560c  call    RtlStringLengthWorkerW_0
0x180125611  mov     ebx, eax
0x180125613  test    eax, eax
0x180125615  js      loc_18012591D
0x18012561b  movzx   eax, word ptr [rsp+180h+var_138]
0x180125620  lea     r9, [rsp+180h+var_118]
0x180125625  add     ax, ax
0x180125628  mov     qword ptr [rsp+180h+var_130+8], r11
0x18012562d  mov     word ptr [rsp+180h+var_130], ax
0x180125632  lea     rcx, [rsp+180h+var_130]
0x180125637  add     ax, 2
0x18012563b  xor     edx, edx
0x18012563d  mov     r8d, 0F003Fh
0x180125643  mov     word ptr [rsp+180h+var_130+2], ax
0x180125648  call    LdrpOpenKey
0x18012564d  mov     ebx, eax
0x18012564f  test    eax, eax
0x180125651  js      loc_180125948
0x180125657  mov     [rsp+180h+Handle], r13
0x18012565c  mov     edx, 8
0x180125661  mov     rcx, gs:60h
0x18012566a  mov     r8d, 200h
0x180125670  mov     rcx, [rcx+30h]
0x180125674  call    RtlAllocateHeap_0
0x180125679  mov     r15, rax
0x18012567c  test    rax, rax
0x18012567f  jnz     short loc_18012568B
0x180125681  mov     ebx, 0C0000017h
0x180125686  jmp     loc_18012591D
0x18012568b  mov     byte ptr [rsp+180h+var_150], r13b
0x180125690  mov     eax, r13d
0x180125693  mov     edi, r13d
0x180125696  mov     rsi, r13
0x180125699  lea     rcx, [rsp+180h+var_110]
0x18012569e  mov     dword ptr [rsp+180h+var_138], eax
0x1801256a2  mov     [rsp+180h+var_158], rcx
0x1801256a7  mov     r9, r15
0x1801256aa  mov     rcx, [rsp+180h+var_118]
0x1801256af  xor     r8d, r8d
0x1801256b2  mov     edx, eax
0x1801256b4  mov     [rsp+180h+var_160], 200h
0x1801256bc  call    NtEnumerateKey
0x1801256c1  mov     r14d, eax
0x1801256c4  test    eax, eax
0x1801256c6  js      loc_18012581A
0x1801256cc  mov     ecx, [r15+0Ch]
0x1801256d0  lea     rax, [rcx+18h]
0x1801256d4  cmp     rax, 200h
0x1801256da  ja      loc_180125801
0x1801256e0  shr     rcx, 1
0x1801256e3  lea     rbx, [r15+10h]
0x1801256e7  xor     eax, eax
0x1801256e9  lea     r9, [rsp+180h+var_140]
0x1801256ee  xor     r8d, r8d
0x1801256f1  mov     rdx, rbx
0x1801256f4  mov     [r15+rcx*2+10h], ax
0x1801256fa  mov     rcx, [rsp+180h+var_120]
0x1801256ff  call    RtlpMuiRegGetInstalledLanguageIndexByName
0x180125704  test    eax, eax
0x180125706  jns     loc_180125801
0x18012570c  mov     rdx, [rbp+80h+String2]; String2
0x180125710  mov     rcx, rbx; String1
0x180125713  call    _wcsicmp
0x180125718  test    eax, eax
0x18012571a  jz      loc_180125801
0x180125720  xorps   xmm0, xmm0
0x180125723  movups  [rsp+180h+var_130], xmm0
0x180125728  test    rbx, rbx
0x18012572b  jz      short loc_18012576B
0x18012572d  lea     r8, [rsp+180h+var_108]
0x180125732  mov     [rsp+180h+var_108], 0
0x18012573b  mov     edx, 7FFFh
0x180125740  mov     rcx, rbx
0x180125743  call    RtlStringLengthWorkerW_0
0x180125748  test    eax, eax
0x18012574a  js      loc_180125801
0x180125750  movzx   eax, word ptr [rsp+180h+var_108]
0x180125755  add     ax, ax
0x180125758  mov     qword ptr [rsp+180h+var_130+8], rbx
0x18012575d  mov     word ptr [rsp+180h+var_130], ax
0x180125762  add     ax, 2
0x180125766  mov     word ptr [rsp+180h+var_130+2], ax
0x18012576b  mov     rdx, [rsp+180h+var_118]
0x180125770  lea     r9, [rsp+180h+Handle]
0x180125775  mov     r8d, 0F003Fh
0x18012577b  lea     rcx, [rsp+180h+var_130]
0x180125780  call    LdrpOpenKey
0x180125785  test    eax, eax
0x180125787  js      short loc_180125801
0x180125789  test    rsi, rsi
0x18012578c  jnz     short loc_1801257A9
0x18012578e  lea     edx, [rsi+0Ah]
0x180125791  call    _MuiRegAllocArray_0
0x180125796  xor     r13d, r13d
0x180125799  mov     rsi, rax
0x18012579c  test    rax, rax
0x18012579f  jz      short loc_18012580C
0x1801257a1  mov     r13d, 0Ah
0x1801257a7  jmp     short loc_1801257EB
0x1801257a9  cmp     edi, r13d
0x1801257ac  jb      short loc_1801257EB
0x1801257ae  lea     edx, [r13+0Ah]
0x1801257b2  call    _MuiRegAllocArray_0
0x1801257b7  mov     rbx, rax
0x1801257ba  test    rax, rax
0x1801257bd  jz      short loc_180125814
0x1801257bf  mov     r8d, r13d; Size
0x1801257c2  mov     rdx, rsi; Src
0x1801257c5  mov     rcx, rax; void *
0x1801257c8  call    memmove
0x1801257cd  mov     rcx, gs:60h
0x1801257d6  mov     r8, rsi
0x1801257d9  xor     edx, edx
0x1801257db  mov     rcx, [rcx+30h]
0x1801257df  call    RtlFreeHeap_0
0x1801257e4  add     r13d, 0Ah
0x1801257e8  mov     rsi, rbx
0x1801257eb  mov     rax, [rsp+180h+Handle]
0x1801257f0  mov     ecx, edi
0x1801257f2  inc     edi
0x1801257f4  mov     [rsi+rcx*8], rax
0x1801257f8  mov     [rsp+180h+Handle], 0
0x180125801  mov     eax, dword ptr [rsp+180h+var_138]
0x180125805  inc     eax
0x180125807  jmp     loc_180125699
0x18012580c  mov     r14d, 0C0000017h
0x180125812  jmp     short loc_18012581D
0x180125814  mov     r14d, 0C0000017h
0x18012581a  xor     r13d, r13d
0x18012581d  mov     rcx, [rsp+180h+Handle]; Handle
0x180125822  test    rcx, rcx
0x180125825  jz      short loc_18012582C
0x180125827  call    NtClose
0x18012582c  cmp     r14d, 8000001Ah
0x180125833  mov     ebx, r13d
0x180125836  cmovnz  ebx, r14d
0x18012583a  test    rsi, rsi
0x18012583d  jz      short loc_1801258A1
0x18012583f  test    edi, edi
0x180125841  jz      short loc_18012588A
0x180125843  test    ebx, ebx
0x180125845  js      short loc_180125871
0x180125847  dec     edi
0x180125849  mov     rcx, [rsi+rdi*8]
0x18012584d  mov     [rsp+180h+Handle], rcx
0x180125852  test    rcx, rcx
0x180125855  jz      short loc_18012586B
0x180125857  mov     byte ptr [rsp+180h+var_150], 1
0x18012585c  call    NtDeleteKey
0x180125861  mov     rcx, [rsp+180h+Handle]; Handle
0x180125866  call    NtClose
0x18012586b  test    edi, edi
0x18012586d  jnz     short loc_180125847
0x18012586f  jmp     short loc_18012588A
0x180125871  dec     edi
0x180125873  mov     rcx, [rsi+rdi*8]; Handle
0x180125877  mov     [rsp+180h+Handle], rcx
0x18012587c  test    rcx, rcx
0x18012587f  jz      short loc_180125886
0x180125881  call    NtClose
0x180125886  test    edi, edi
0x180125888  jnz     short loc_180125871
0x18012588a  mov     rcx, gs:60h
0x180125893  mov     r8, rsi
0x180125896  xor     edx, edx
0x180125898  mov     rcx, [rcx+30h]
0x18012589c  call    RtlFreeHeap_0
0x1801258a1  test    ebx, ebx
0x1801258a3  js      short loc_18012591D
0x1801258a5  cmp     byte ptr [rsp+180h+var_150], r13b
0x1801258aa  jz      short loc_18012591D
0x1801258ac  xor     edx, edx
0x1801258ae  xor     r8d, r8d
0x1801258b1  lea     ecx, [rdx+2]
0x1801258b4  call    ZwGetMUIRegistryInfo
0x1801258b9  call    RtlCleanUpTEBLangLists
0x1801258be  call    RtlpInitMuiCriticalSection
0x1801258c3  lea     rcx, RegistryInfoCritSect
0x1801258ca  call    RtlEnterCriticalSection
0x1801258cf  mov     rcx, cs:g_RegInfo
0x1801258d6  mov     edx, 0FFFh
0x1801258db  call    RtlpMuiRegFreeRegistryInfo
0x1801258e0  mov     ebx, eax
0x1801258e2  test    eax, eax
0x1801258e4  js      short loc_180125911
0x1801258e6  cmp     cs:g_RegInfo, r13
0x1801258ed  jz      short loc_18012590A
0x1801258ef  mov     rcx, gs:60h
0x1801258f8  xor     edx, edx
0x1801258fa  mov     r8, cs:g_RegInfo
0x180125901  mov     rcx, [rcx+30h]
0x180125905  call    RtlFreeHeap_0
0x18012590a  mov     cs:g_RegInfo, r13
0x180125911  lea     rcx, RegistryInfoCritSect
0x180125918  call    RtlLeaveCriticalSection
0x18012591d  mov     rcx, [rsp+180h+var_118]; Handle
0x180125922  test    rcx, rcx
0x180125925  jz      short loc_18012592C
0x180125927  call    NtClose
0x18012592c  test    r15, r15
0x18012592f  jz      short loc_180125948
0x180125931  mov     rcx, gs:60h
0x18012593a  mov     r8, r15
0x18012593d  xor     edx, edx
0x18012593f  mov     rcx, [rcx+30h]
0x180125943  call    RtlFreeHeap_0
0x180125948  mov     eax, ebx
0x18012594a  mov     rcx, [rbp+80h+var_40]
0x18012594e  xor     rcx, rsp; StackCookie
0x180125951  call    __security_check_cookie
0x180125956  add     rsp, 150h
0x18012595d  pop     r15
0x18012595f  pop     r14
0x180125961  pop     r13
0x180125963  pop     rdi
0x180125964  pop     rsi
0x180125965  pop     rbx
0x180125966  pop     rbp
0x180125967  retn
```
