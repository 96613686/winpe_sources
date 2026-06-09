# CWapDPU::Initialize(uchar *,ulong)

- ea: `0x180028e40`
- end: `0x180028fd5`
- name: `?Initialize@CWapDPU@@UEAAJPEAEK@Z`
- size: `405`
- prototype: `__int64 __fastcall(CWapDPU *this, unsigned __int8 *, int)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180014330`
- `0x1800168f4`
- `0x180017e94`
- `0x1800187d0`
- `0x180028e40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180028e73`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180028e73`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028f95`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028f95`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180028f3e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180028f73`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180028f3e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180028f73`

## pseudocode

```c
__int64 __fastcall CWapDPU::Initialize(CWapDPU *this, unsigned __int8 *a2, int a3)
{
  struct _RTL_CRITICAL_SECTION *v6; // rbx
  HRESULT Instance; // esi
  unsigned int i; // r15d
  __int64 v9; // rdx
  _BYTE v11[16]; // [rsp+40h] [rbp-78h] BYREF
  _BYTE v12[64]; // [rsp+50h] [rbp-68h] BYREF

  v6 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 72);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  if ( a2 )
  {
    if ( a3 != 32 )
    {
      Instance = -2147024809;
      goto LABEL_17;
    }
    *((_QWORD *)this + 8) = *((_QWORD *)a2 + 1);
    *((_QWORD *)this + 6) = *(_QWORD *)a2;
    if ( *((_QWORD *)a2 + 3) && *((_DWORD *)a2 + 4) )
    {
      for ( i = 0; i < *((_DWORD *)a2 + 4); ++i )
      {
        if ( __eh34_try(-1, 0) )
        {
          __eh34_scope_strut(0);
          v9 = *((_QWORD *)a2 + 3) + 16LL * i;
          std::pair<std::wstring const,std::wstring>::pair<std::wstring const,std::wstring>(v12, v9, v9 + 8);
          std::_Hash<stdext::_Hmap_traits<std::wstring,std::wstring,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::emplace<std::pair<std::wstring const,std::wstring> &>(
            (char *)this + 112,
            v11,
            v12);
        }
        if ( __eh34_catch(0) )
        {
          if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
          {
            Instance = -2147024882;
            __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_180028FC9);
            goto LABEL_17;
          }
        }
        if ( !v11[8] )
        {
          Instance = -2147024809;
          std::pair<std::wstring const,std::wstring>::~pair<std::wstring const,std::wstring>(v12);
          goto LABEL_17;
        }
        std::pair<std::wstring const,std::wstring>::~pair<std::wstring const,std::wstring>(v12);
      }
    }
  }
  Instance = 0;
  if ( *((_QWORD *)this + 1)
    || (Instance = CoCreateInstance(
                     &GUID_66d0db14_5638_475f_a386_629522d8c461,
                     0,
                     1u,
                     &GUID_56a4bdd5_835a_4dd5_95b5_44805ca37db0,
                     (LPVOID *)this + 1),
        Instance >= 0) )
  {
    if ( *((_QWORD *)this + 4)
      || (Instance = CoCreateInstance(
                       &GUID_9c62d90d_9c14_400a_942a_404aba5e1f38,
                       0,
                       1u,
                       &GUID_d4c5e807_d2bf_49a0_83a4_f9c7d57e08d8,
                       (LPVOID *)this + 4),
          Instance >= 0) )
    {
      *((_DWORD *)this + 10) = 0;
    }
  }
LABEL_17:
  if ( v6 )
    LeaveCriticalSection(v6);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180028e40  mov     [rsp+arg_10], rbx
0x180028e45  push    rsi
0x180028e46  push    r14
0x180028e48  push    r15
0x180028e4a  sub     rsp, 0A0h
0x180028e51  mov     rax, cs:__security_cookie
0x180028e58  xor     rax, rsp
0x180028e5b  mov     [rsp+0B8h+var_28], rax
0x180028e63  mov     r15d, r8d
0x180028e66  mov     rsi, rdx
0x180028e69  mov     r14, rcx
0x180028e6c  lea     rbx, [rcx+48h]
0x180028e70  mov     rcx, rbx; lpCriticalSection
0x180028e73  call    cs:__imp_EnterCriticalSection
0x180028e7a  nop     dword ptr [rax+rax+00h]
0x180028e7f  mov     [rsp+0B8h+var_80], rbx
0x180028e84  test    rsi, rsi
0x180028e87  jz      loc_180028F1A
0x180028e8d  cmp     r15d, 20h ; ' '
0x180028e91  jz      short loc_180028E9D
0x180028e93  mov     esi, 80070057h
0x180028e98  jmp     loc_180028F8D
0x180028e9d  mov     rax, [rsi+8]
0x180028ea1  mov     [r14+40h], rax
0x180028ea5  mov     rax, [rsi]
0x180028ea8  mov     [r14+30h], rax
0x180028eac  cmp     qword ptr [rsi+18h], 0
0x180028eb1  jz      short loc_180028F1A
0x180028eb3  cmp     dword ptr [rsi+10h], 0
0x180028eb7  jz      short loc_180028F1A
0x180028eb9  xor     r15d, r15d
0x180028ebc  cmp     r15d, [rsi+10h]
0x180028ec0  jnb     short loc_180028F1A
0x180028ec2  mov     edx, r15d
0x180028ec5  shl     rdx, 4
0x180028ec9  add     rdx, [rsi+18h]
0x180028ecd  lea     r8, [rdx+8]
0x180028ed1  lea     rcx, [rsp+0B8h+var_68]
0x180028ed6  call    ??$?0AEBQEBGAEBQEBG$0A@@?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@QEAA@AEBQEBG0@Z; std::pair<std::wstring const,std::wstring>::pair<std::wstring const,std::wstring>(ushort const * const &,ushort const * const &)
0x180028edb  nop
0x180028edc  lea     rcx, [r14+70h]
0x180028ee0  lea     r8, [rsp+0B8h+var_68]
0x180028ee5  lea     rdx, [rsp+0B8h+var_78]
0x180028eea  call    ??$emplace@AEAU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@?$_Hash@V?$_Hmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@stdext@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@@std@@_N@1@AEAU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@1@@Z; std::_Hash<stdext::_Hmap_traits<std::wstring,std::wstring,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::emplace<std::pair<std::wstring const,std::wstring> &>(std::pair<std::wstring const,std::wstring> &)
0x180028eef  cmp     [rsp+0B8h+var_70], 0
0x180028ef4  jnz     short loc_180028F0B
0x180028ef6  mov     esi, 80070057h
0x180028efb  lea     rcx, [rsp+0B8h+var_68]; void *
0x180028f00  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@QEAA@XZ; std::pair<std::wstring const,std::wstring>::~pair<std::wstring const,std::wstring>(void)
0x180028f05  nop
0x180028f06  jmp     loc_180028F8D
0x180028f0b  lea     rcx, [rsp+0B8h+var_68]; void *
0x180028f10  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@QEAA@XZ; std::pair<std::wstring const,std::wstring>::~pair<std::wstring const,std::wstring>(void)
0x180028f15  inc     r15d
0x180028f18  jmp     short loc_180028EBC
0x180028f1a  xor     esi, esi
0x180028f1c  lea     rax, [r14+8]
0x180028f20  cmp     [rax], rsi
0x180028f23  jnz     short loc_180028F50
0x180028f25  mov     [rsp+0B8h+ppv], rax; ppv
0x180028f2a  lea     r9, _GUID_56a4bdd5_835a_4dd5_95b5_44805ca37db0; riid
0x180028f31  xor     edx, edx; pUnkOuter
0x180028f33  lea     r8d, [rsi+1]; dwClsContext
0x180028f37  lea     rcx, _GUID_66d0db14_5638_475f_a386_629522d8c461; rclsid
0x180028f3e  call    cs:__imp_CoCreateInstance
0x180028f45  nop     dword ptr [rax+rax+00h]
0x180028f4a  mov     esi, eax
0x180028f4c  test    eax, eax
0x180028f4e  js      short loc_180028F8D
0x180028f50  lea     rax, [r14+20h]
0x180028f54  cmp     qword ptr [rax], 0
0x180028f58  jnz     short loc_180028F85
0x180028f5a  mov     [rsp+0B8h+ppv], rax; ppv
0x180028f5f  lea     r9, _GUID_d4c5e807_d2bf_49a0_83a4_f9c7d57e08d8; riid
0x180028f66  xor     edx, edx; pUnkOuter
0x180028f68  lea     r8d, [rdx+1]; dwClsContext
0x180028f6c  lea     rcx, _GUID_9c62d90d_9c14_400a_942a_404aba5e1f38; rclsid
0x180028f73  call    cs:__imp_CoCreateInstance
0x180028f7a  nop     dword ptr [rax+rax+00h]
0x180028f7f  mov     esi, eax
0x180028f81  test    eax, eax
0x180028f83  js      short loc_180028F8D
0x180028f85  mov     dword ptr [r14+28h], 0
0x180028f8d  test    rbx, rbx
0x180028f90  jz      short loc_180028FA1
0x180028f92  mov     rcx, rbx; lpCriticalSection
0x180028f95  call    cs:__imp_LeaveCriticalSection
0x180028f9c  nop     dword ptr [rax+rax+00h]
0x180028fa1  mov     eax, esi
0x180028fa3  mov     rcx, [rsp+0B8h+var_28]
0x180028fab  xor     rcx, rsp; StackCookie
0x180028fae  call    __security_check_cookie
0x180028fb3  mov     rbx, [rsp+0B8h+arg_10]
0x180028fbb  add     rsp, 0A0h
0x180028fc2  pop     r15
0x180028fc4  pop     r14
0x180028fc6  pop     rsi
0x180028fc7  retn
0x180028fc9  mov     rbx, [rsp+0B8h+var_80]
0x180028fce  mov     esi, [rsp+0B8h+var_88]
0x180028fd2  jmp     short loc_180028F8D
```
