# CDims::Notify(ulong)

- ea: `0x1800078e0`
- end: `0x180007dd9`
- name: `?Notify@CDims@@UEAAXK@Z`
- size: `1273`
- prototype: `void __fastcall(CDims *this, int)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800018f0`
- `0x180001c10`
- `0x1800021c0`
- `0x180002cc0`
- `0x180002f70`
- `0x1800078e0`
- `0x18000a360`
- `0x18000aac8`
- `0x18000ad30`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800079d7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800079d7`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180007a50`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180007aa8`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180007bc2`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180007d89`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180007a50`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180007aa8`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180007bc2`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180007d89`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180007da5`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180007da5`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000794b`
- `ntdll!RtlReleaseSRWLockShared` at `0x180007964`
- `ntdll!RtlReleaseSRWLockShared` at `0x180007a25`
- `ntdll!RtlReleaseSRWLockShared` at `0x180007a76`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000794b`
- `ntdll!RtlReleaseSRWLockShared` at `0x180007964`
- `ntdll!RtlReleaseSRWLockShared` at `0x180007a25`
- `ntdll!RtlReleaseSRWLockShared` at `0x180007a76`
- `ntdll!RtlAcquireSRWLockShared` at `0x180007931`
- `ntdll!RtlAcquireSRWLockShared` at `0x180007a09`
- `ntdll!RtlAcquireSRWLockShared` at `0x180007931`
- `ntdll!RtlAcquireSRWLockShared` at `0x180007a09`

## string_xrefs

- `0x180007b1a`: `dimsroam.dll`
- `0x180007d13`: `dimsroam.dll`
- `0x180007c5c`: `pautoenr.dll`

## pseudocode

```c
void __fastcall CDims::Notify(CDims *this, int a2)
{
  char *v3; // rbx
  char *v4; // rcx
  unsigned int v5; // esi
  CDims *v6; // rcx
  int v7; // r8d
  int v8; // r9d
  int v9; // esi
  __int32 v10; // esi
  char *v11; // rsi
  void (__fastcall ***v12)(_QWORD, __int64); // rcx
  char v13; // al
  __int16 v14; // r15
  bool IsNetConnected; // al
  int v16; // r8d
  int v17; // r9d
  unsigned int v18; // ecx
  char v19; // [rsp+30h] [rbp-98h]
  char v20; // [rsp+31h] [rbp-97h]
  char v21; // [rsp+32h] [rbp-96h]
  unsigned int v23; // [rsp+38h] [rbp-90h]
  LPCWSTR lpSubKey; // [rsp+40h] [rbp-88h] BYREF
  char v25; // [rsp+48h] [rbp-80h]
  char v26; // [rsp+49h] [rbp-7Fh]
  CDims *v27; // [rsp+58h] [rbp-70h]
  LPCWSTR *p_lpSubKey; // [rsp+68h] [rbp-60h]
  char *v30; // [rsp+78h] [rbp-50h]
  bool v31; // [rsp+80h] [rbp-48h]

  v27 = this;
  v3 = (char *)this + *(int *)(*((_QWORD *)this + 8) + 8LL) + 64;
  RtlAcquireSRWLockShared(&v3[*(int *)(*(_QWORD *)v3 + 4LL)]);
  v4 = &v3[*(int *)(*(_QWORD *)v3 + 4LL)];
  if ( *((_BYTE *)this + 220) )
  {
    RtlReleaseSRWLockShared(v4);
    return;
  }
  v19 = 0;
  v20 = 0;
  v21 = 0;
  v5 = 0;
  RtlReleaseSRWLockShared(v4);
  if ( (a2 & 0x700) != 0 )
    CDims::RefreshPolicyAndStartWatchers(this);
  lpSubKey = L"SOFTWARE\\Microsoft\\Volatile-KeyRoam-EXCLUSIVE";
  v25 = 0;
  v26 = *((_BYTE *)this + 8);
  p_lpSubKey = &lpSubKey;
  if ( CDims::_CSessionBounceLock::Lock((CDims::_CSessionBounceLock *)&lpSubKey) )
  {
    if ( !*((_BYTE *)this + 8) )
    {
      v9 = a2;
      if ( (a2 & 0x400) != 0 )
      {
        v10 = _InterlockedExchange((volatile __int32 *)this + 54, 0);
        if ( !v10 || GetTickCount() - v10 > 0x36EE80 )
        {
          a2 &= ~0x400u;
          v11 = (char *)this + *(int *)(*((_QWORD *)this + 8) + 8LL) + 64;
          RtlAcquireSRWLockShared(&v11[*(int *)(*(_QWORD *)v11 + 4LL)]);
          v12 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 22);
          if ( !v12 )
          {
            RtlReleaseSRWLockShared(&v11[*(int *)(*(_QWORD *)v11 + 4LL)]);
            if ( !v25 )
              return;
LABEL_30:
            RegDeleteKeyExW((HKEY)((v26 != 0) - 0x7FFFFFFFLL), lpSubKey, 0, 0);
            return;
          }
          (**v12)(v12, 2048);
          RtlReleaseSRWLockShared(&v11[*(int *)(*(_QWORD *)v11 + 4LL)]);
        }
        v9 = a2;
      }
      if ( !v9 )
      {
        if ( !v25 )
          return;
        goto LABEL_30;
      }
      v13 = _InterlockedExchangeAdd((volatile signed __int32 *)this + 50, 0);
      v5 = v9 & 0xFFFFFFFD;
      if ( v5 && (v13 & 0x41) != 0 )
      {
        v21 = 1;
        v30 = (char *)this + 208;
        v31 = _InterlockedIncrement((volatile signed __int32 *)this + 52) == 1;
        if ( v31 )
        {
          if ( !*((_QWORD *)this + 2) )
          {
            CDims::CProvider::Load(
              (CDims *)((char *)this + 16),
              L"dimsroam.dll",
              "DimsRoamEntry",
              *((_DWORD *)this + 56));
            v19 = 1;
          }
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          {
            WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_5aeb05ffed9b311d494cef63d73c85d5_Traceguids, v5);
          }
          CDims::CProvider::operator()((_DWORD)this + 16, v5, v7, v8, *((_DWORD *)this + 56));
        }
        _InterlockedDecrement((volatile signed __int32 *)this + 52);
      }
    }
    v23 = a2 & 0xFFFFEFFE;
    if ( !v23 )
    {
      if ( !v25 )
        return;
      goto LABEL_30;
    }
    v14 = _InterlockedExchangeAdd((volatile signed __int32 *)this + 51, 0);
    IsNetConnected = CDims::p_IsNetConnected(v6);
    v18 = *((_DWORD *)this + 56);
    if ( IsNetConnected )
    {
      if ( v18 > 3 )
        LogReport(DM_LOG_INFO_NET_CONNECTED, 0, 0);
      if ( (v14 & 0x8020) != 0x8000 )
      {
        v30 = (char *)this + 212;
        v31 = _InterlockedIncrement((volatile signed __int32 *)this + 53) == 1;
        v20 = 1;
        if ( v31 )
        {
          if ( !*((_QWORD *)this + 5) )
            CDims::CProvider::Load(
              (CDims *)((char *)this + 40),
              L"pautoenr.dll",
              "DimsProvEntry",
              *((_DWORD *)this + 56));
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          {
            WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_5aeb05ffed9b311d494cef63d73c85d5_Traceguids, v23);
          }
          CDims::CProvider::operator()((_DWORD)this + 40, v23, v16, v17, *((_DWORD *)this + 56));
        }
        _InterlockedDecrement((volatile signed __int32 *)this + 53);
      }
    }
    else if ( v18 > 3 )
    {
      LogReport(DM_LOG_INFO_NET_DISCONNECTED, 0, 0);
    }
    if ( v19 )
    {
      v30 = (char *)this + 208;
      v31 = _InterlockedIncrement((volatile signed __int32 *)this + 52) == 1;
      if ( v31 )
      {
        if ( !*((_QWORD *)this + 2) )
          CDims::CProvider::Load((CDims *)((char *)this + 16), L"dimsroam.dll", "DimsRoamEntry", *((_DWORD *)this + 56));
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_5aeb05ffed9b311d494cef63d73c85d5_Traceguids, v5);
        CDims::CProvider::operator()((_DWORD)this + 16, v5, v16, v17, *((_DWORD *)this + 56));
      }
      _InterlockedDecrement((volatile signed __int32 *)this + 52);
    }
  }
  if ( v25 )
    RegDeleteKeyExW((HKEY)((v26 != 0) - 0x7FFFFFFFLL), lpSubKey, 0, 0);
  if ( !v20 && !v21 )
    Sleep(0x1F4u);
}

```

## disassembly

```asm
0x1800078e0  mov     [rsp+arg_10], rbx
0x1800078e5  mov     [rsp+arg_18], rsi
0x1800078ea  push    rdi
0x1800078eb  push    r12
0x1800078ed  push    r13
0x1800078ef  push    r14
0x1800078f1  push    r15
0x1800078f3  sub     rsp, 0A0h
0x1800078fa  mov     rax, cs:__security_cookie
0x180007901  xor     rax, rsp
0x180007904  mov     [rsp+0C8h+var_30], rax
0x18000790c  mov     rdi, rcx
0x18000790f  mov     [rsp+0C8h+var_70], rcx
0x180007914  mov     [rsp+0C8h+var_90], edx
0x180007918  mov     rax, [rcx+40h]
0x18000791c  movsxd  rdx, dword ptr [rax+8]
0x180007920  lea     rbx, [rcx+40h]
0x180007924  add     rbx, rdx
0x180007927  mov     rax, [rbx]
0x18000792a  movsxd  rcx, dword ptr [rax+4]
0x18000792e  add     rcx, rbx
0x180007931  call    cs:__imp_RtlAcquireSRWLockShared
0x180007937  mov     rax, [rbx]
0x18000793a  movsxd  rcx, dword ptr [rax+4]
0x18000793e  add     rcx, rbx
0x180007941  xor     ebx, ebx
0x180007943  cmp     [rdi+0DCh], bl
0x180007949  jz      short loc_180007956
0x18000794b  call    cs:__imp_RtlReleaseSRWLockShared
0x180007951  jmp     loc_180007DAC
0x180007956  mov     [rsp+0C8h+var_98], bl
0x18000795a  mov     [rsp+0C8h+var_97], bl
0x18000795e  mov     [rsp+0C8h+var_96], bl
0x180007962  mov     esi, ebx
0x180007964  call    cs:__imp_RtlReleaseSRWLockShared
0x18000796a  test    [rsp+0C8h+var_90], 700h
0x180007972  jz      short loc_18000797D
0x180007974  mov     rcx, rdi; this
0x180007977  call    ?RefreshPolicyAndStartWatchers@CDims@@QEAAXXZ; CDims::RefreshPolicyAndStartWatchers(void)
0x18000797c  nop
0x18000797d  lea     rax, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Volatile-KeyRoam-E"...
0x180007984  mov     [rsp+0C8h+lpSubKey], rax
0x180007989  mov     [rsp+0C8h+var_80], bl
0x18000798d  mov     al, [rdi+8]
0x180007990  mov     [rsp+0C8h+var_7F], al
0x180007994  lea     rax, [rsp+0C8h+lpSubKey]
0x180007999  mov     [rsp+0C8h+var_60], rax
0x18000799e  lea     rcx, [rsp+0C8h+lpSubKey]; this
0x1800079a3  call    ?Lock@_CSessionBounceLock@CDims@@QEAA_NXZ; CDims::_CSessionBounceLock::Lock(void)
0x1800079a8  mov     [rsp+0C8h+var_58], al
0x1800079ac  test    al, al
0x1800079ae  jz      loc_180007D65
0x1800079b4  cmp     [rdi+8], bl
0x1800079b7  jnz     loc_180007B82
0x1800079bd  mov     esi, [rsp+0C8h+var_90]
0x1800079c1  bt      esi, 0Ah
0x1800079c5  jnb     loc_180007A80
0x1800079cb  mov     esi, ebx
0x1800079cd  xchg    esi, [rdi+0D8h]
0x1800079d3  test    esi, esi
0x1800079d5  jz      short loc_1800079EA
0x1800079d7  call    cs:__imp_GetTickCount
0x1800079dd  sub     eax, esi
0x1800079df  cmp     eax, 36EE80h
0x1800079e4  jbe     loc_180007A7C
0x1800079ea  btr     [rsp+0C8h+var_90], 0Ah
0x1800079f0  mov     rax, [rdi+40h]
0x1800079f4  movsxd  rsi, dword ptr [rax+8]
0x1800079f8  add     rsi, 40h ; '@'
0x1800079fc  add     rsi, rdi
0x1800079ff  mov     rax, [rsi]
0x180007a02  movsxd  rcx, dword ptr [rax+4]
0x180007a06  add     rcx, rsi
0x180007a09  call    cs:__imp_RtlAcquireSRWLockShared
0x180007a0f  mov     rcx, [rdi+0B0h]
0x180007a16  test    rcx, rcx
0x180007a19  jnz     short loc_180007A5C
0x180007a1b  mov     rax, [rsi]
0x180007a1e  movsxd  rcx, dword ptr [rax+4]
0x180007a22  add     rcx, rsi
0x180007a25  call    cs:__imp_RtlReleaseSRWLockShared
0x180007a2b  nop
0x180007a2c  cmp     [rsp+0C8h+var_80], bl
0x180007a30  jz      short loc_180007A57
0x180007a32  mov     al, [rsp+0C8h+var_7F]
0x180007a36  neg     al
0x180007a38  sbb     rcx, rcx
0x180007a3b  neg     rcx
0x180007a3e  add     rcx, 0FFFFFFFF80000001h; hKey
0x180007a45  xor     r9d, r9d; Reserved
0x180007a48  xor     r8d, r8d; samDesired
0x180007a4b  mov     rdx, [rsp+0C8h+lpSubKey]; lpSubKey
0x180007a50  call    cs:__imp_RegDeleteKeyExW
0x180007a56  nop
0x180007a57  jmp     loc_180007DAC
0x180007a5c  mov     rax, [rcx]
0x180007a5f  mov     edx, 800h
0x180007a64  mov     rax, [rax]
0x180007a67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a6c  mov     rax, [rsi]
0x180007a6f  movsxd  rcx, dword ptr [rax+4]
0x180007a73  add     rcx, rsi
0x180007a76  call    cs:__imp_RtlReleaseSRWLockShared
0x180007a7c  mov     esi, [rsp+0C8h+var_90]
0x180007a80  test    esi, esi
0x180007a82  jnz     short loc_180007AB4
0x180007a84  cmp     [rsp+0C8h+var_80], bl
0x180007a88  jz      short loc_180007AAF
0x180007a8a  mov     al, [rsp+0C8h+var_7F]
0x180007a8e  neg     al
0x180007a90  sbb     rcx, rcx
0x180007a93  neg     rcx
0x180007a96  add     rcx, 0FFFFFFFF80000001h; hKey
0x180007a9d  xor     r9d, r9d; Reserved
0x180007aa0  xor     r8d, r8d; samDesired
0x180007aa3  mov     rdx, [rsp+0C8h+lpSubKey]; lpSubKey
0x180007aa8  call    cs:__imp_RegDeleteKeyExW
0x180007aae  nop
0x180007aaf  jmp     loc_180007DAC
0x180007ab4  mov     eax, ebx
0x180007ab6  lock xadd [rdi+0C8h], eax
0x180007abe  and     esi, 0FFFFFFFDh
0x180007ac1  jz      loc_180007B82
0x180007ac7  test    al, 41h
0x180007ac9  jz      loc_180007B82
0x180007acf  mov     r14d, 1
0x180007ad5  mov     [rsp+0C8h+var_96], r14b
0x180007ada  lea     r15, [rdi+0D0h]
0x180007ae1  mov     [rsp+0C8h+var_50], r15
0x180007ae6  mov     eax, r14d
0x180007ae9  lock xadd [r15], eax
0x180007aee  add     eax, r14d
0x180007af1  cmp     eax, r14d
0x180007af4  setz    al
0x180007af7  mov     [rsp+0C8h+var_48], al
0x180007afe  test    al, al
0x180007b00  jz      short loc_180007B75
0x180007b02  lea     r12, [rdi+10h]
0x180007b06  cmp     [r12], rbx
0x180007b0a  jnz     short loc_180007B2E
0x180007b0c  mov     r9d, [rdi+0E0h]; unsigned int
0x180007b13  lea     r8, aDimsroamentry; "DimsRoamEntry"
0x180007b1a  lea     rdx, aDimsroamDll; "dimsroam.dll"
0x180007b21  mov     rcx, r12; this
0x180007b24  call    ?Load@CProvider@CDims@@QEAAXPEBGPEBDK@Z; CDims::CProvider::Load(ushort const *,char const *,ulong)
0x180007b29  mov     [rsp+0C8h+var_98], r14b
0x180007b2e  lea     r13, WPP_GLOBAL_Control
0x180007b35  mov     rcx, cs:WPP_GLOBAL_Control
0x180007b3c  cmp     rcx, r13
0x180007b3f  jz      short loc_180007B5F
0x180007b41  test    byte ptr [rcx+1Ch], 10h
0x180007b45  jz      short loc_180007B5F
0x180007b47  mov     edx, 0Ch
0x180007b4c  mov     r9d, esi
0x180007b4f  lea     r8, WPP_5aeb05ffed9b311d494cef63d73c85d5_Traceguids
0x180007b56  mov     rcx, [rcx+10h]
0x180007b5a  call    WPP_SF_D
0x180007b5f  mov     eax, [rdi+0E0h]
0x180007b65  mov     [rsp+0C8h+var_A8], eax
0x180007b69  mov     edx, esi
0x180007b6b  mov     rcx, r12
0x180007b6e  call    ??RCProvider@CDims@@QEAAXKPEBX_KK@Z; CDims::CProvider::operator()(ulong,void const *,unsigned __int64,ulong)
0x180007b73  jmp     short loc_180007B7C
0x180007b75  lea     r13, WPP_GLOBAL_Control
0x180007b7c  lock dec dword ptr [r15]
0x180007b80  jmp     short loc_180007B8F
0x180007b82  mov     r14d, 1
0x180007b88  lea     r13, WPP_GLOBAL_Control
0x180007b8f  mov     eax, [rsp+0C8h+var_90]
0x180007b93  and     eax, 0FFFFEFFEh
0x180007b98  mov     [rsp+0C8h+var_90], eax
0x180007b9c  jnz     short loc_180007BCE
0x180007b9e  cmp     [rsp+0C8h+var_80], bl
0x180007ba2  jz      short loc_180007BC9
0x180007ba4  mov     al, [rsp+0C8h+var_7F]
0x180007ba8  neg     al
0x180007baa  sbb     rcx, rcx
0x180007bad  neg     rcx
0x180007bb0  add     rcx, 0FFFFFFFF80000001h; hKey
0x180007bb7  xor     r9d, r9d; Reserved
0x180007bba  xor     r8d, r8d; samDesired
0x180007bbd  mov     rdx, [rsp+0C8h+lpSubKey]; lpSubKey
0x180007bc2  call    cs:__imp_RegDeleteKeyExW
0x180007bc8  nop
0x180007bc9  jmp     loc_180007DAC
0x180007bce  mov     r15d, ebx
0x180007bd1  lock xadd [rdi+0CCh], r15d
0x180007bda  call    ?p_IsNetConnected@CDims@@AEAA_NXZ; CDims::p_IsNetConnected(void)
0x180007bdf  mov     ecx, [rdi+0E0h]
0x180007be5  test    al, al
0x180007be7  jz      loc_180007CB4
0x180007bed  cmp     ecx, 3
0x180007bf0  jbe     short loc_180007C03
0x180007bf2  xor     r8d, r8d
0x180007bf5  xor     edx, edx
0x180007bf7  lea     rcx, DM_LOG_INFO_NET_CONNECTED
0x180007bfe  call    _LogReport
0x180007c03  and     r15d, 8020h
0x180007c0a  cmp     r15d, 8000h
0x180007c11  jz      loc_180007CCA
0x180007c17  lea     r15, [rdi+0D4h]
0x180007c1e  mov     [rsp+0C8h+var_50], r15
0x180007c23  mov     eax, r14d
0x180007c26  lock xadd [r15], eax
0x180007c2b  add     eax, r14d
0x180007c2e  cmp     eax, r14d
0x180007c31  setz    al
0x180007c34  mov     [rsp+0C8h+var_48], al
0x180007c3b  mov     [rsp+0C8h+var_97], r14b
0x180007c40  test    al, al
0x180007c42  jz      short loc_180007CAE
0x180007c44  lea     r12, [rdi+28h]
0x180007c48  cmp     [r12], rbx
0x180007c4c  jnz     short loc_180007C6B
0x180007c4e  mov     r9d, [rdi+0E0h]; unsigned int
0x180007c55  lea     r8, aDimsproventry; "DimsProvEntry"
0x180007c5c  lea     rdx, aPautoenrDll; "pautoenr.dll"
0x180007c63  mov     rcx, r12; this
0x180007c66  call    ?Load@CProvider@CDims@@QEAAXPEBGPEBDK@Z; CDims::CProvider::Load(ushort const *,char const *,ulong)
0x180007c6b  mov     rcx, cs:WPP_GLOBAL_Control
0x180007c72  cmp     rcx, r13
0x180007c75  jz      short loc_180007C97
0x180007c77  test    byte ptr [rcx+1Ch], 10h
0x180007c7b  jz      short loc_180007C97
0x180007c7d  mov     edx, 0Dh
0x180007c82  mov     r9d, [rsp+0C8h+var_90]
0x180007c87  lea     r8, WPP_5aeb05ffed9b311d494cef63d73c85d5_Traceguids
0x180007c8e  mov     rcx, [rcx+10h]
0x180007c92  call    WPP_SF_D
0x180007c97  mov     eax, [rdi+0E0h]
0x180007c9d  mov     [rsp+0C8h+var_A8], eax
0x180007ca1  mov     edx, [rsp+0C8h+var_90]
0x180007ca5  mov     rcx, r12
0x180007ca8  call    ??RCProvider@CDims@@QEAAXKPEBX_KK@Z; CDims::CProvider::operator()(ulong,void const *,unsigned __int64,ulong)
0x180007cad  nop
0x180007cae  lock dec dword ptr [r15]
0x180007cb2  jmp     short loc_180007CCA
0x180007cb4  cmp     ecx, 3
0x180007cb7  jbe     short loc_180007CCA
0x180007cb9  xor     r8d, r8d
0x180007cbc  xor     edx, edx
0x180007cbe  lea     rcx, DM_LOG_INFO_NET_DISCONNECTED
0x180007cc5  call    _LogReport
0x180007cca  cmp     [rsp+0C8h+var_98], bl
0x180007cce  jz      loc_180007D65
0x180007cd4  lea     r15, [rdi+0D0h]
0x180007cdb  mov     [rsp+0C8h+var_50], r15
0x180007ce0  mov     eax, r14d
0x180007ce3  lock xadd [r15], eax
0x180007ce8  add     eax, r14d
0x180007ceb  cmp     eax, r14d
0x180007cee  setz    al
0x180007cf1  mov     [rsp+0C8h+var_48], al
0x180007cf8  test    al, al
0x180007cfa  jz      short loc_180007D61
0x180007cfc  lea     r14, [rdi+10h]
0x180007d00  cmp     [r14], rbx
0x180007d03  jnz     short loc_180007D22
0x180007d05  mov     r9d, [rdi+0E0h]; unsigned int
0x180007d0c  lea     r8, aDimsroamentry; "DimsRoamEntry"
0x180007d13  lea     rdx, aDimsroamDll; "dimsroam.dll"
0x180007d1a  mov     rcx, r14; this
0x180007d1d  call    ?Load@CProvider@CDims@@QEAAXPEBGPEBDK@Z; CDims::CProvider::Load(ushort const *,char const *,ulong)
0x180007d22  mov     rcx, cs:WPP_GLOBAL_Control
0x180007d29  cmp     rcx, r13
0x180007d2c  jz      short loc_180007D4C
0x180007d2e  test    byte ptr [rcx+1Ch], 10h
0x180007d32  jz      short loc_180007D4C
0x180007d34  mov     edx, 0Eh
0x180007d39  mov     r9d, esi
0x180007d3c  lea     r8, WPP_5aeb05ffed9b311d494cef63d73c85d5_Traceguids
0x180007d43  mov     rcx, [rcx+10h]
0x180007d47  call    WPP_SF_D
0x180007d4c  mov     eax, [rdi+0E0h]
0x180007d52  mov     [rsp+0C8h+var_A8], eax
0x180007d56  mov     edx, esi
0x180007d58  mov     rcx, r14
0x180007d5b  call    ??RCProvider@CDims@@QEAAXKPEBX_KK@Z; CDims::CProvider::operator()(ulong,void const *,unsigned __int64,ulong)
0x180007d60  nop
0x180007d61  lock dec dword ptr [r15]
0x180007d65  cmp     [rsp+0C8h+var_80], bl
0x180007d69  jz      short loc_180007D90
0x180007d6b  mov     al, [rsp+0C8h+var_7F]
0x180007d6f  neg     al
0x180007d71  sbb     rcx, rcx
0x180007d74  neg     rcx
0x180007d77  add     rcx, 0FFFFFFFF80000001h; hKey
0x180007d7e  xor     r9d, r9d; Reserved
0x180007d81  xor     r8d, r8d; samDesired
0x180007d84  mov     rdx, [rsp+0C8h+lpSubKey]; lpSubKey
0x180007d89  call    cs:__imp_RegDeleteKeyExW
0x180007d8f  nop
0x180007d90  jmp     short loc_180007D94
0x180007d92  xor     ebx, ebx
0x180007d94  cmp     [rsp+0C8h+var_97], bl
0x180007d98  jnz     short loc_180007DAC
0x180007d9a  cmp     [rsp+0C8h+var_96], bl
0x180007d9e  jnz     short loc_180007DAC
0x180007da0  mov     ecx, 1F4h; dwMilliseconds
0x180007da5  call    cs:__imp_Sleep
  ... truncated ...
```
