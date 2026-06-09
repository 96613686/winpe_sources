# container::ObjectManagerProvider::SetupDirectory(Schema::Containers::Definition::ObjectDirectory const &,void *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180026f60`
- end: `0x18002724b`
- name: `?SetupDirectory@ObjectManagerProvider@container@@YAXAEBUObjectDirectory@Definition@Containers@Schema@@PEAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `747`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180026e7c`
- `0x180026f60`

## callees

- `0x180002ad0`
- `0x180002ee4`
- `0x1800051b0`
- `0x18000b4bc`
- `0x18000be30`
- `0x18000d668`
- `0x1800227ec`
- `0x180022c94`
- `0x180026588`
- `0x180026830`
- `0x180026b68`
- `0x180026de4`
- `0x180026f60`
- `0x180027438`

## import_xrefs

- `ntdll!NtCreateDirectoryObjectEx` at `0x180027131`
- `ntdll!NtCreateDirectoryObjectEx` at `0x180027131`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027162`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800271f6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027162`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800271f6`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
int __fastcall container::ObjectManagerProvider::SetupDirectory(__int64 *a1, __int64 a2, _QWORD *a3)
{
  int v3; // r15d
  void *v5; // r14
  __int64 v6; // rcx
  __int64 v7; // rax
  __int64 v8; // r8
  int v9; // edi
  char *v10; // rbx
  unsigned __int64 v11; // rdx
  __int64 *v12; // rax
  int v13; // eax
  const struct Schema::Containers::Definition::ObjectSymlink *v14; // rdi
  void *v15; // r8
  int result; // eax
  __int64 v17; // r15
  __int64 i; // rbx
  container::ObjectManagerProvider *v19; // r15
  container::ObjectManagerProvider *j; // rbx
  bool v21[4]; // [rsp+40h] [rbp-C0h] BYREF
  int v22; // [rsp+44h] [rbp-BCh] BYREF
  void *v23; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE hObject; // [rsp+50h] [rbp-B0h] BYREF
  const struct Schema::Containers::Definition::ObjectSymlink *v25; // [rsp+58h] [rbp-A8h]
  char *v26; // [rsp+60h] [rbp-A0h]
  __int64 *v27; // [rsp+68h] [rbp-98h] BYREF
  _OWORD v28[2]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v29[32]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v30[32]; // [rsp+B0h] [rbp-50h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v32[32]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v33[64]; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v34[32]; // [rsp+170h] [rbp+70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+C8h]

  v3 = a2;
  v25 = 0;
  v28[0] = 0;
  v28[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v28[0]) = 0;
  v5 = 0;
  v23 = 0;
  v6 = a3[2];
  if ( v6 == 0x7FFFFFFFFFFFFFFELL )
    std::_Xlen_string();
  if ( a3[3] > 7u )
    a3 = (_QWORD *)*a3;
  std::wstring::wstring(v29, a2, a3, a3, v6, L"\\", 1);
  v7 = std::operator+<unsigned short>(v30, v29, a1);
  std::wstring::operator=(v28, v7);
  std::wstring::~wstring(v30);
  std::wstring::~wstring(v29);
  if ( a1[6] )
  {
    LOBYTE(v8) = *((_DWORD *)a1 + 16) != 2;
    container::ObjectManager::GetDirectorySecurityDescriptor(a1 + 4, &v23, v8);
    v5 = v23;
  }
  v9 = *((_DWORD *)a1 + 16);
  hObject = 0;
  v10 = 0;
  v26 = 0;
  if ( v9 )
  {
    windows_wrappers::ObjectAttributes::ObjectAttributes((unsigned int)&ObjectAttributes, (unsigned int)v28, 0, 0, 0);
    v10 = (char *)container::ObjectManager::OpenDir(&ObjectAttributes, (struct _OBJECT_ATTRIBUTES *)3, v9 != 2);
    v26 = v10;
    if ( !v10 )
    {
      std::wstring::~wstring(v32);
      v25 = 0;
LABEL_17:
      if ( v5 )
        operator delete(v5, v11);
      return std::wstring::~wstring(v28);
    }
    std::wstring::~wstring(v32);
  }
  v22 = 208;
  v21[0] = v10 != 0;
  if ( (unsigned __int64)a1[3] <= 7 )
    v12 = a1;
  else
    v12 = (__int64 *)*a1;
  v27 = v12;
  ContainerProvider::CreateObDirectory<unsigned short const *,unsigned long &,bool>(&v27, &v22, v21);
  windows_wrappers::ObjectAttributes::ObjectAttributes((unsigned int)v33, (_DWORD)a1, 208, v3, (__int64)v5);
  v13 = NtCreateDirectoryObjectEx(&hObject, 983055, v33, v10);
  if ( v13 <= -1 )
    wil::details::in1diag3::Throw_NtStatus(
      retaddr,
      (void *)0x198,
      (unsigned int)"onecore\\base\\gendrv\\silos\\container\\ob_provider.cpp",
      (const char *)(unsigned int)v13,
      0);
  v14 = (const struct Schema::Containers::Definition::ObjectSymlink *)hObject;
  std::wstring::~wstring(v34);
  if ( (unsigned __int64)(v10 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v10);
  v25 = v14;
  if ( !v14 )
    goto LABEL_17;
  v17 = a1[13];
  for ( i = a1[12]; i != v17; i += 120 )
    container::ObjectManagerProvider::SetupDirectory(i, v14, v28);
  v19 = (container::ObjectManagerProvider *)a1[10];
  for ( j = (container::ObjectManagerProvider *)a1[9]; j != v19; j = (container::ObjectManagerProvider *)((char *)j + 112) )
    container::ObjectManagerProvider::SetupSymlink(j, v14, v15);
  if ( v5 )
    operator delete(v5, v11);
  result = std::wstring::~wstring(v28);
  if ( v14 != (const struct Schema::Containers::Definition::ObjectSymlink *)-1LL )
    return CloseHandle(v14);
  return result;
}

```

## disassembly

```asm
0x180026f60  mov     [rsp-8+arg_8], rbx
0x180026f65  push    rbp
0x180026f66  push    rsi
0x180026f67  push    rdi
0x180026f68  push    r14
0x180026f6a  push    r15
0x180026f6c  lea     rbp, [rsp-0A0h]
0x180026f74  sub     rsp, 1A0h
0x180026f7b  mov     rax, cs:__security_cookie
0x180026f82  xor     rax, rsp
0x180026f85  mov     [rbp+0C0h+var_30], rax
0x180026f8c  mov     r15, rdx
0x180026f8f  mov     rsi, rcx
0x180026f92  mov     [rsp+1C0h+var_168], 0
0x180026f9b  xorps   xmm0, xmm0
0x180026f9e  movups  [rsp+1C0h+var_150], xmm0
0x180026fa3  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180026fab  movdqu  [rbp+0C0h+var_140], xmm1
0x180026fb0  xor     eax, eax
0x180026fb2  mov     word ptr [rsp+1C0h+var_150], ax
0x180026fb7  xor     r14d, r14d
0x180026fba  mov     [rsp+1C0h+var_178], r14
0x180026fbf  mov     rcx, [r8+10h]
0x180026fc3  mov     rax, 7FFFFFFFFFFFFFFEh
0x180026fcd  sub     rax, rcx
0x180026fd0  cmp     rax, 1
0x180026fd4  jb      loc_180027245
0x180026fda  cmp     qword ptr [r8+18h], 7
0x180026fdf  jbe     short loc_180026FE4
0x180026fe1  mov     r8, [r8]
0x180026fe4  mov     [rsp+1C0h+var_190], 1
0x180026fed  lea     rax, asc_180037DD0; "\\"
0x180026ff4  mov     [rsp+1C0h+var_198], rax
0x180026ff9  mov     qword ptr [rsp+1C0h+var_1A0], rcx
0x180026ffe  mov     r9, r8
0x180027001  lea     rcx, [rbp+0C0h+var_130]
0x180027005  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x18002700a  nop
0x18002700b  mov     r8, rsi
0x18002700e  lea     rdx, [rbp+0C0h+var_130]
0x180027012  lea     rcx, [rbp+0C0h+var_110]
0x180027016  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x18002701b  mov     rdx, rax
0x18002701e  lea     rcx, [rsp+1C0h+var_150]
0x180027023  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180027028  lea     rcx, [rbp+0C0h+var_110]
0x18002702c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180027031  nop
0x180027032  lea     rcx, [rbp+0C0h+var_130]
0x180027036  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002703b  lea     rcx, [rsi+20h]
0x18002703f  cmp     qword ptr [rcx+10h], 0
0x180027044  jz      short loc_18002705D
0x180027046  cmp     dword ptr [rsi+40h], 2
0x18002704a  setnz   r8b
0x18002704e  lea     rdx, [rsp+1C0h+var_178]
0x180027053  call    ?GetDirectorySecurityDescriptor@ObjectManager@container@@YAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAVSecurityDescriptor@windows_wrappers@@_N@Z; container::ObjectManager::GetDirectorySecurityDescriptor(std::wstring const &,windows_wrappers::SecurityDescriptor &,bool)
0x180027058  mov     r14, [rsp+1C0h+var_178]
0x18002705d  mov     edi, [rsi+40h]
0x180027060  mov     [rsp+1C0h+hObject], 0
0x180027069  xor     ebx, ebx
0x18002706b  mov     [rsp+1C0h+var_160], rbx
0x180027070  test    edi, edi
0x180027072  jz      short loc_1800270C7
0x180027074  mov     qword ptr [rsp+1C0h+var_1A0], rbx
0x180027079  xor     r9d, r9d
0x18002707c  xor     r8d, r8d
0x18002707f  lea     rdx, [rsp+1C0h+var_150]
0x180027084  lea     rcx, [rbp+0C0h+ObjectAttributes]
0x180027088  call    ??0ObjectAttributes@windows_wrappers@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KQEAX1@Z; windows_wrappers::ObjectAttributes::ObjectAttributes(std::wstring const &,ulong,void * const,void * const)
0x18002708d  nop
0x18002708e  cmp     edi, 2
0x180027091  setnz   r8b; unsigned int
0x180027095  lea     edx, [rbx+3]; struct _OBJECT_ATTRIBUTES *
0x180027098  lea     rcx, [rbp+0C0h+ObjectAttributes]; ObjectAttributes
0x18002709c  call    ?OpenDir@ObjectManager@container@@YAPEAXPEAU_OBJECT_ATTRIBUTES@@K_N@Z; container::ObjectManager::OpenDir(_OBJECT_ATTRIBUTES *,ulong,bool)
0x1800270a1  mov     rbx, rax
0x1800270a4  mov     [rsp+1C0h+var_160], rax
0x1800270a9  lea     rcx, [rbp+0C0h+var_B0]
0x1800270ad  test    rax, rax
0x1800270b0  jnz     short loc_1800270C2
0x1800270b2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800270b7  nop
0x1800270b8  mov     [rsp+1C0h+var_168], rbx
0x1800270bd  jmp     loc_180027178
0x1800270c2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800270c7  mov     edi, 0D0h
0x1800270cc  mov     [rsp+1C0h+var_17C], edi
0x1800270d0  test    rbx, rbx
0x1800270d3  setnz   [rsp+1C0h+var_180]
0x1800270d8  cmp     qword ptr [rsi+18h], 7
0x1800270dd  jbe     short loc_1800270E4
0x1800270df  mov     rax, [rsi]
0x1800270e2  jmp     short loc_1800270E7
0x1800270e4  mov     rax, rsi
0x1800270e7  mov     [rsp+1C0h+var_158], rax
0x1800270ec  lea     r8, [rsp+1C0h+var_180]
0x1800270f1  lea     rdx, [rsp+1C0h+var_17C]
0x1800270f6  lea     rcx, [rsp+1C0h+var_158]
0x1800270fb  call    ??$CreateObDirectory@PEBGAEAK_N@ContainerProvider@@SAX$$QEAPEBGAEAK$$QEA_N@Z; ContainerProvider::CreateObDirectory<ushort const *,ulong &,bool>(ushort const * &&,ulong &,bool &&)
0x180027100  mov     qword ptr [rsp+1C0h+var_1A0], r14
0x180027105  mov     r9, r15
0x180027108  mov     r8d, edi
0x18002710b  mov     rdx, rsi
0x18002710e  lea     rcx, [rbp+0C0h+var_90]
0x180027112  call    ??0ObjectAttributes@windows_wrappers@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KQEAX1@Z; windows_wrappers::ObjectAttributes::ObjectAttributes(std::wstring const &,ulong,void * const,void * const)
0x180027117  nop
0x180027118  mov     [rsp+1C0h+var_1A0], 0; int
0x180027120  mov     r9, rbx
0x180027123  lea     r8, [rbp+0C0h+var_90]
0x180027127  mov     edx, 0F000Fh
0x18002712c  lea     rcx, [rsp+1C0h+hObject]
0x180027131  call    cs:__imp_NtCreateDirectoryObjectEx
0x180027138  nop     dword ptr [rax+rax+00h]
0x18002713d  cmp     eax, 0FFFFFFFFh
0x180027140  jle     loc_180027229
0x180027146  mov     rdi, [rsp+1C0h+hObject]
0x18002714b  lea     rcx, [rbp+0C0h+var_50]
0x18002714f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180027154  nop
0x180027155  lea     rax, [rbx-1]
0x180027159  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002715d  ja      short loc_18002716E
0x18002715f  mov     rcx, rbx; hObject
0x180027162  call    cs:__imp_CloseHandle
0x180027169  nop     dword ptr [rax+rax+00h]
0x18002716e  mov     [rsp+1C0h+var_168], rdi
0x180027173  test    rdi, rdi
0x180027176  jnz     short loc_180027193
0x180027178  test    r14, r14
0x18002717b  jz      short loc_180027186
0x18002717d  mov     rcx, r14; void *
0x180027180  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180027185  nop
0x180027186  lea     rcx, [rsp+1C0h+var_150]
0x18002718b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180027190  nop
0x180027191  jmp     short loc_180027202
0x180027193  mov     r15, [rsi+68h]
0x180027197  mov     rbx, [rsi+60h]
0x18002719b  jmp     short loc_1800271B1
0x18002719d  lea     r8, [rsp+1C0h+var_150]
0x1800271a2  mov     rdx, rdi
0x1800271a5  mov     rcx, rbx
0x1800271a8  call    ?SetupDirectory@ObjectManagerProvider@container@@YAXAEBUObjectDirectory@Definition@Containers@Schema@@PEAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; container::ObjectManagerProvider::SetupDirectory(Schema::Containers::Definition::ObjectDirectory const &,void *,std::wstring const &)
0x1800271ad  add     rbx, 78h ; 'x'
0x1800271b1  cmp     rbx, r15
0x1800271b4  jnz     short loc_18002719D
0x1800271b6  mov     r15, [rsi+50h]
0x1800271ba  mov     rbx, [rsi+48h]
0x1800271be  jmp     short loc_1800271CF
0x1800271c0  mov     rdx, rdi; struct Schema::Containers::Definition::ObjectSymlink *
0x1800271c3  mov     rcx, rbx; this
0x1800271c6  call    ?SetupSymlink@ObjectManagerProvider@container@@YAXAEBUObjectSymlink@Definition@Containers@Schema@@PEAX@Z; container::ObjectManagerProvider::SetupSymlink(Schema::Containers::Definition::ObjectSymlink const &,void *)
0x1800271cb  add     rbx, 70h ; 'p'
0x1800271cf  cmp     rbx, r15
0x1800271d2  jnz     short loc_1800271C0
0x1800271d4  test    r14, r14
0x1800271d7  jz      short loc_1800271E2
0x1800271d9  mov     rcx, r14; void *
0x1800271dc  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800271e1  nop
0x1800271e2  lea     rcx, [rsp+1C0h+var_150]
0x1800271e7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800271ec  nop
0x1800271ed  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800271f1  jz      short loc_180027202
0x1800271f3  mov     rcx, rdi; hObject
0x1800271f6  call    cs:__imp_CloseHandle
0x1800271fd  nop     dword ptr [rax+rax+00h]
0x180027202  mov     rcx, [rbp+0C0h+var_30]
0x180027209  xor     rcx, rsp; StackCookie
0x18002720c  call    __security_check_cookie
0x180027211  mov     rbx, [rsp+1C0h+arg_8]
0x180027219  add     rsp, 1A0h
0x180027220  pop     r15
0x180027222  pop     r14
0x180027224  pop     rdi
0x180027225  pop     rsi
0x180027226  pop     rbp
0x180027227  retn
0x180027229  mov     rcx, [rbp+0C8h]; this
0x180027230  mov     r9d, eax; char *
0x180027233  lea     r8, aOnecoreBaseGen_3; "onecore\\base\\gendrv\\silos\\container"...
0x18002723a  mov     edx, 198h; void *
0x18002723f  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
0x180027245  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
