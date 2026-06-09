# CShareEventContext::EndEvent(void)

- ea: `0x18000a3d0`
- end: `0x18000a65f`
- name: `?EndEvent@CShareEventContext@@UEAAXXZ`
- size: `655`
- prototype: `void __fastcall(CShareEventContext *__hidden this)`
- caller_count: `0`
- callee_count: `13`
- tags: `broker_com_uri`

## callees

- `0x1800096cc`
- `0x180009704`
- `0x18000990c`
- `0x18000a3d0`
- `0x18000be78`
- `0x18000bf80`
- `0x18000eae4`
- `0x18000eeb4`
- `0x18000ef38`
- `0x18000f454`
- `0x180029894`
- `0x180035b40`
- `0x180037010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000a45b`
- `KERNEL32!GetLastError` at `0x18000a4ff`
- `KERNEL32!GetLastError` at `0x18000a55c`
- `KERNEL32!GetLastError` at `0x18000a45b`
- `KERNEL32!GetLastError` at `0x18000a4ff`
- `KERNEL32!GetLastError` at `0x18000a55c`
- `KERNEL32!LocalFree` at `0x18000a615`
- `KERNEL32!LocalFree` at `0x18000a615`
- `KERNEL32!GetComputerNameExW` at `0x18000a552`
- `KERNEL32!GetComputerNameExW` at `0x18000a552`
- `CLUSAPI!CloseCluster` at `0x18000a631`
- `CLUSAPI!CloseCluster` at `0x18000a631`
- `CLUSAPI!OpenClusterResource` at `0x18000a4f1`
- `CLUSAPI!OpenClusterResource` at `0x18000a4f1`
- `CLUSAPI!OpenCluster` at `0x18000a44d`
- `CLUSAPI!OpenCluster` at `0x18000a44d`
- `CLUSAPI!CloseClusterResource` at `0x18000a623`
- `CLUSAPI!CloseClusterResource` at `0x18000a623`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CShareEventContext::EndEvent(CShareEventContext *this)
{
  DWORD LastError; // edi
  struct _HRESOURCE *v3; // r14
  bool v4; // al
  struct _HCLUSTER *v5; // r15
  unsigned __int64 last_of; // rax
  __int64 v7; // r11
  __int64 v8; // rax
  __int64 v9; // rdx
  const WCHAR *v10; // rdx
  __int64 v11; // rdx
  __int64 v12; // rdx
  MI_Instance *v13; // r12
  __int64 v14; // rcx
  HLOCAL hMem; // [rsp+30h] [rbp-69h] BYREF
  DWORD nSize; // [rsp+38h] [rbp-61h] BYREF
  LPCWSTR lpszResourceName[4]; // [rsp+40h] [rbp-59h] BYREF
  _BYTE v18[32]; // [rsp+60h] [rbp-39h] BYREF
  _BYTE v19[32]; // [rsp+80h] [rbp-19h] BYREF
  WCHAR Buffer[16]; // [rsp+A0h] [rbp+7h] BYREF

  nSize = 16;
  hMem = 0;
  if ( *((_DWORD *)this + 76) == -1 )
    return;
  LastError = 0;
  v3 = 0;
  v4 = *((_BYTE *)this + 225) && *((_BYTE *)this + 224) == 1;
  if ( *((_BYTE *)this + 240) && v4 )
  {
    v5 = OpenCluster(0);
    if ( v5 || (LastError = GetLastError()) == 0 )
    {
      std::wstring::wstring(v18, *((_QWORD *)this + 29));
      std::wstring::wstring(lpszResourceName, v18);
      if ( std::wstring::find_first_of(v18) != -1 )
      {
        last_of = std::wstring::find_last_of(v18);
        if ( last_of != -1 && last_of > 1 )
        {
          v8 = std::wstring::substr(v18, v19, v7 + 1, last_of - 1);
          std::wstring::operator=(lpszResourceName, v8);
          LOBYTE(v9) = 1;
          std::wstring::_Tidy(v19, v9, 0);
        }
      }
      v10 = (const WCHAR *)lpszResourceName;
      if ( lpszResourceName[3] >= (LPCWSTR)8 )
        v10 = lpszResourceName[0];
      v3 = OpenClusterResource(v5, v10);
      if ( !v3 )
        LastError = GetLastError();
      LOBYTE(v11) = 1;
      std::wstring::_Tidy(lpszResourceName, v11, 0);
      LOBYTE(v12) = 1;
      std::wstring::_Tidy(v18, v12, 0);
      if ( !LastError )
        LastError = GetResourceName(v3);
    }
    goto LABEL_22;
  }
  v5 = 0;
  if ( !GetComputerNameExW(ComputerNamePhysicalNetBIOS, Buffer, &nSize) )
  {
    LastError = GetLastError();
LABEL_22:
    v13 = (MI_Instance *)((char *)this + 128);
    (*(void (__fastcall **)(char *, __int64))(*((_QWORD *)this + 16) + 112LL))((char *)this + 128, 4);
LABEL_24:
    if ( !LastError )
    {
      hMem = v13;
      if ( !(*(unsigned int (__fastcall **)(char *, __int64, HLOCAL *))(*((_QWORD *)this + 5) + 80LL))(
              (char *)this + 40,
              1,
              &hMem) )
      {
        v14 = *((_QWORD *)this + 2);
        if ( v14 )
        {
          if ( *(_QWORD *)v14 )
            (*(void (__fastcall **)(__int64, char *, _QWORD, _QWORD))(*(_QWORD *)v14 + 16LL))(
              v14,
              (char *)this + 40,
              0,
              0);
        }
      }
    }
    goto LABEL_29;
  }
  v13 = (MI_Instance *)((char *)this + 128);
  if ( !(unsigned int)MSFT_NfsShare_Set_NetworkName((char *)this + 128, Buffer) )
    goto LABEL_24;
LABEL_29:
  MI_Instance_Destruct((MI_Instance *)((char *)this + 40));
  MI_Instance_Destruct(v13);
  if ( v3 )
    CloseClusterResource(v3);
  if ( v5 )
    CloseCluster(v5);
}

```

## disassembly

```asm
0x18000a3d0  mov     [rsp-8+arg_8], rbx
0x18000a3d5  mov     [rsp-8+arg_10], rsi
0x18000a3da  push    rbp
0x18000a3db  push    rdi
0x18000a3dc  push    r12
0x18000a3de  push    r14
0x18000a3e0  push    r15
0x18000a3e2  lea     rbp, [rsp-37h]
0x18000a3e7  sub     rsp, 0D0h
0x18000a3ee  mov     rax, cs:__security_cookie
0x18000a3f5  xor     rax, rsp
0x18000a3f8  mov     [rbp+57h+var_30], rax
0x18000a3fc  mov     rbx, rcx
0x18000a3ff  mov     [rbp+57h+nSize], 10h
0x18000a406  xor     esi, esi
0x18000a408  mov     [rbp+57h+hMem], rsi
0x18000a40c  cmp     dword ptr [rcx+130h], 0FFFFFFFFh
0x18000a413  jz      loc_18000A637
0x18000a419  xor     edi, edi
0x18000a41b  xor     r14d, r14d
0x18000a41e  cmp     [rcx+0E1h], sil
0x18000a425  jz      short loc_18000A434
0x18000a427  cmp     byte ptr [rcx+0E0h], 1
0x18000a42e  jnz     short loc_18000A434
0x18000a430  mov     al, 1
0x18000a432  jmp     short loc_18000A436
0x18000a434  xor     al, al
0x18000a436  cmp     [rcx+0F0h], sil
0x18000a43d  jz      loc_18000A543
0x18000a443  test    al, al
0x18000a445  jz      loc_18000A543
0x18000a44b  xor     ecx, ecx; lpszClusterName
0x18000a44d  call    cs:__imp_OpenCluster
0x18000a453  mov     r15, rax
0x18000a456  test    rax, rax
0x18000a459  jnz     short loc_18000A46B
0x18000a45b  call    cs:__imp_GetLastError
0x18000a461  mov     edi, eax
0x18000a463  test    eax, eax
0x18000a465  jnz     loc_18000A56F
0x18000a46b  mov     rdx, [rbx+0E8h]
0x18000a472  lea     rcx, [rbp+57h+var_90]
0x18000a476  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18000a47b  nop
0x18000a47c  lea     rdx, [rbp+57h+var_90]
0x18000a480  lea     rcx, [rbp+57h+lpszResourceName]
0x18000a484  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000a489  nop
0x18000a48a  lea     rcx, [rbp+57h+var_90]
0x18000a48e  call    ?find_first_of@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KPEBG_K@Z; std::wstring::find_first_of(ushort const *,unsigned __int64)
0x18000a493  mov     r11, rax
0x18000a496  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000a49a  jz      short loc_18000A4E0
0x18000a49c  lea     rcx, [rbp+57h+var_90]
0x18000a4a0  call    ?find_last_of@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KPEBG_K@Z; std::wstring::find_last_of(ushort const *,unsigned __int64)
0x18000a4a5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000a4a9  jz      short loc_18000A4E0
0x18000a4ab  cmp     rax, 1
0x18000a4af  jbe     short loc_18000A4E0
0x18000a4b1  lea     r9, [rax-1]
0x18000a4b5  lea     r8, [r11+1]
0x18000a4b9  lea     rdx, [rbp+57h+var_70]
0x18000a4bd  lea     rcx, [rbp+57h+var_90]
0x18000a4c1  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x18000a4c6  mov     rdx, rax
0x18000a4c9  lea     rcx, [rbp+57h+lpszResourceName]
0x18000a4cd  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18000a4d2  xor     r8d, r8d
0x18000a4d5  mov     dl, 1
0x18000a4d7  lea     rcx, [rbp+57h+var_70]
0x18000a4db  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000a4e0  lea     rdx, [rbp+57h+lpszResourceName]
0x18000a4e4  cmp     [rbp+57h+var_98], 8
0x18000a4e9  cmovnb  rdx, [rbp+57h+lpszResourceName]; lpszResourceName
0x18000a4ee  mov     rcx, r15; hCluster
0x18000a4f1  call    cs:__imp_OpenClusterResource
0x18000a4f7  mov     r14, rax
0x18000a4fa  test    rax, rax
0x18000a4fd  jnz     short loc_18000A507
0x18000a4ff  call    cs:__imp_GetLastError
0x18000a505  mov     edi, eax
0x18000a507  xor     r8d, r8d
0x18000a50a  mov     dl, 1
0x18000a50c  lea     rcx, [rbp+57h+lpszResourceName]
0x18000a510  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000a515  nop
0x18000a516  xor     r8d, r8d
0x18000a519  mov     dl, 1
0x18000a51b  lea     rcx, [rbp+57h+var_90]
0x18000a51f  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000a524  test    edi, edi
0x18000a526  jnz     short loc_18000A56F
0x18000a528  lea     rdx, [rbp+57h+hMem]
0x18000a52c  mov     rcx, r14; hResource
0x18000a52f  call    GetResourceName
0x18000a534  mov     edi, eax
0x18000a536  mov     rsi, [rbp+57h+hMem]
0x18000a53a  test    eax, eax
0x18000a53c  jnz     short loc_18000A56F
0x18000a53e  mov     rdx, rsi
0x18000a541  jmp     short loc_18000A56A
0x18000a543  xor     r15d, r15d
0x18000a546  lea     r8, [rbp+57h+nSize]; nSize
0x18000a54a  lea     rdx, [rbp+57h+Buffer]; lpBuffer
0x18000a54e  lea     ecx, [r15+4]; NameType
0x18000a552  call    cs:__imp_GetComputerNameExW
0x18000a558  test    eax, eax
0x18000a55a  jnz     short loc_18000A58D
0x18000a55c  call    cs:__imp_GetLastError
0x18000a562  mov     edi, eax
0x18000a564  test    eax, eax
0x18000a566  jnz     short loc_18000A56F
0x18000a568  xor     edx, edx
0x18000a56a  test    rdx, rdx
0x18000a56d  jnz     short loc_18000A591
0x18000a56f  lea     r12, [rbx+80h]
0x18000a576  mov     rax, [r12]
0x18000a57a  mov     edx, 4
0x18000a57f  mov     rcx, r12
0x18000a582  mov     rax, [rax+70h]
0x18000a586  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a58b  jmp     short loc_18000A5A4
0x18000a58d  lea     rdx, [rbp+57h+Buffer]
0x18000a591  lea     r12, [rbx+80h]
0x18000a598  mov     rcx, r12
0x18000a59b  call    MSFT_NfsShare_Set_NetworkName
0x18000a5a0  test    eax, eax
0x18000a5a2  jnz     short loc_18000A5FC
0x18000a5a4  test    edi, edi
0x18000a5a6  jnz     short loc_18000A5FC
0x18000a5a8  mov     [rbp+57h+hMem], r12
0x18000a5ac  lea     rdi, [rbx+28h]
0x18000a5b0  mov     rax, [rdi]
0x18000a5b3  mov     [rsp+0F0h+var_D0], 0
0x18000a5bb  mov     r9d, 0Fh
0x18000a5c1  lea     r8, [rbp+57h+hMem]
0x18000a5c5  lea     edx, [r9-0Eh]
0x18000a5c9  mov     rcx, rdi
0x18000a5cc  mov     rax, [rax+50h]
0x18000a5d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a5d5  test    eax, eax
0x18000a5d7  jnz     short loc_18000A5FC
0x18000a5d9  mov     rcx, [rbx+10h]
0x18000a5dd  test    rcx, rcx
0x18000a5e0  jz      short loc_18000A5FC
0x18000a5e2  mov     rax, [rcx]
0x18000a5e5  test    rax, rax
0x18000a5e8  jz      short loc_18000A5FC
0x18000a5ea  xor     r9d, r9d
0x18000a5ed  xor     r8d, r8d
0x18000a5f0  mov     rdx, rdi
0x18000a5f3  mov     rax, [rax+10h]
0x18000a5f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a5fc  lea     rcx, [rbx+28h]; self
0x18000a600  call    MI_Instance_Destruct
0x18000a605  mov     rcx, r12; self
0x18000a608  call    MI_Instance_Destruct
0x18000a60d  test    rsi, rsi
0x18000a610  jz      short loc_18000A61B
0x18000a612  mov     rcx, rsi; hMem
0x18000a615  call    cs:__imp_LocalFree
0x18000a61b  test    r14, r14
0x18000a61e  jz      short loc_18000A629
0x18000a620  mov     rcx, r14; hResource
0x18000a623  call    cs:__imp_CloseClusterResource
0x18000a629  test    r15, r15
0x18000a62c  jz      short loc_18000A637
0x18000a62e  mov     rcx, r15; hCluster
0x18000a631  call    cs:__imp_CloseCluster
0x18000a637  mov     rcx, [rbp+57h+var_30]
0x18000a63b  xor     rcx, rsp; StackCookie
0x18000a63e  call    __security_check_cookie
0x18000a643  lea     r11, [rsp+0F0h+var_20]
0x18000a64b  mov     rbx, [r11+38h]
0x18000a64f  mov     rsi, [r11+40h]
0x18000a653  mov     rsp, r11
0x18000a656  pop     r15
0x18000a658  pop     r14
0x18000a65a  pop     r12
0x18000a65c  pop     rdi
0x18000a65d  pop     rbp
0x18000a65e  retn
```
