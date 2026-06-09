# Windows::Compat::Inventory::Service::WinRtHost::GetNextAppInfo(Windows::Compat::Inventory::Service::WinRtHost::RpcCallState &,ushort *,ushort *,ushort *,ushort *)

- ea: `0x1800c450c`
- end: `0x1800c483a`
- name: `?GetNextAppInfo@WinRtHost@Service@Inventory@Compat@Windows@@AEAAJAEAURpcCallState@12345@PEAG111@Z`
- size: `814`
- prototype: `__int64 __fastcall(Windows::Compat::Inventory::Service::WinRtHost *__hidden this, struct Windows::Compat::Inventory::Service::WinRtHost::RpcCallState *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800c4d68`

## callees

- `0x180006e54`
- `0x1800152d0`
- `0x18002d068`
- `0x18002e010`
- `0x1800c441c`
- `0x1800c450c`

## string_xrefs

- `0x1800c4768`: `onecore\base\appcompat\inventory\service\winrt\lib\winrthost.cpp`
- `0x1800c47a8`: `onecore\base\appcompat\inventory\service\winrt\lib\winrthost.cpp`
- `0x1800c47e8`: `onecore\base\appcompat\inventory\service\winrt\lib\winrthost.cpp`
- `0x1800c4828`: `onecore\base\appcompat\inventory\service\winrt\lib\winrthost.cpp`
- `0x1800c474d`: `Windows::Compat::Inventory::Service::WinRtHost::GetNextAppInfo`
- `0x1800c478d`: `Windows::Compat::Inventory::Service::WinRtHost::GetNextAppInfo`
- `0x1800c47cd`: `Windows::Compat::Inventory::Service::WinRtHost::GetNextAppInfo`
- `0x1800c480d`: `Windows::Compat::Inventory::Service::WinRtHost::GetNextAppInfo`

## pseudocode

```c
__int64 __fastcall Windows::Compat::Inventory::Service::WinRtHost::GetNextAppInfo(
        Windows::Compat::Inventory::Service::WinRtHost *this,
        struct Windows::Compat::Inventory::Service::WinRtHost::RpcCallState *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        unsigned __int16 *a6)
{
  __int64 v9; // rdx
  unsigned __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // rbx
  unsigned __int16 *v13; // rax
  __int64 v14; // r10
  __int64 v15; // r8
  __int64 v16; // rcx
  __int64 v17; // r9
  unsigned __int16 *v18; // rdx
  unsigned int v19; // edi
  _QWORD *v20; // rax
  __int64 v21; // rcx
  __int64 v22; // r9
  unsigned __int16 *v23; // rcx
  unsigned int v24; // edx
  __int64 v25; // r9
  int v26; // edi
  _QWORD *v27; // rax
  __int64 v29; // rcx
  __int64 v30; // r9
  unsigned __int16 *v31; // rcx
  unsigned int v32; // edx
  __int64 v33; // r9
  int v34; // edi
  _QWORD *v35; // rax
  unsigned __int16 *v37; // rcx
  unsigned int v38; // edx
  __int64 v39; // r8
  int v40; // ebx
  unsigned int v42; // eax
  unsigned int v43; // eax
  unsigned int v44; // eax
  unsigned int v45; // eax
  int v46; // [rsp+20h] [rbp-48h]
  int v47; // [rsp+20h] [rbp-48h]
  int v48; // [rsp+20h] [rbp-48h]
  int v49; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  do
  {
    v9 = *((_QWORD *)a2 + 5);
    v10 = *((unsigned int *)a2 + 8);
    if ( v10 >= 0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*(_QWORD *)(v9 + 24) - *(_QWORD *)(v9 + 16)) >> 5) )
      return 2147942659LL;
    *((_DWORD *)a2 + 8) = v10 + 1;
    v11 = *(_QWORD *)(v9 + 16);
    if ( 0xCCCCCCCCCCCCCCCDuLL * ((*(_QWORD *)(v9 + 24) - v11) >> 5) <= v10 )
      std::vector<Windows::Compat::Inventory::Service::Win32AppInfo>::_Xrange();
    v12 = v11 + 160 * v10;
  }
  while ( !(unsigned __int8)Windows::Compat::Inventory::Service::WinRtHost::AppCanBeShownToUser(a2, v12) );
  if ( *(_QWORD *)(v12 + 24) <= 7u )
    v13 = (unsigned __int16 *)v12;
  else
    v13 = *(unsigned __int16 **)v12;
  v14 = 2147483646;
  v15 = 260;
  v16 = 2147483646;
  v17 = 260;
  do
  {
    if ( !v16 )
      break;
    if ( !*v13 )
      break;
    *a3++ = *v13++;
    --v16;
    --v17;
  }
  while ( v17 );
  v18 = a3 - 1;
  v19 = v17 == 0 ? 0x8007007A : 0;
  if ( v17 )
    v18 = a3;
  *v18 = 0;
  if ( !v17 )
  {
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::Service::WinRtHost::GetNextAppInfo",
      171,
      "failed [%#x]",
      -2147024774);
    v42 = wil::verify_hresult<long>(v19);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xAB,
      (unsigned int)"onecore\\base\\appcompat\\inventory\\service\\winrt\\lib\\winrthost.cpp",
      (const char *)v42,
      v46);
  }
  v20 = (_QWORD *)(v12 + 32);
  if ( *(_QWORD *)(v12 + 56) > 7u )
    v20 = (_QWORD *)*v20;
  v21 = 2147483646;
  v22 = 260;
  do
  {
    if ( !v21 )
      break;
    if ( !*(_WORD *)v20 )
      break;
    *a4 = *(_WORD *)v20;
    v20 = (_QWORD *)((char *)v20 + 2);
    ++a4;
    --v21;
    --v22;
  }
  while ( v22 );
  v23 = a4 - 1;
  if ( v22 )
    v23 = a4;
  v24 = v22 == 0 ? 0x8007007A : 0;
  *v23 = 0;
  v25 = -v22;
  v26 = v25 != 0 ? v24 : 0;
  if ( v26 < 0 )
  {
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::Service::WinRtHost::GetNextAppInfo",
      175,
      "failed [%#x]",
      v25 != 0 ? v24 : 0);
    v43 = wil::verify_hresult<long>((unsigned int)v26);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xAF,
      (unsigned int)"onecore\\base\\appcompat\\inventory\\service\\winrt\\lib\\winrthost.cpp",
      (const char *)v43,
      v47);
  }
  v27 = (_QWORD *)(v12 + 64);
  if ( *(_QWORD *)(v12 + 88) > 7u )
    v27 = (_QWORD *)*v27;
  v29 = 2147483646;
  v30 = 260;
  do
  {
    if ( !v29 )
      break;
    if ( !*(_WORD *)v27 )
      break;
    *a5 = *(_WORD *)v27;
    v27 = (_QWORD *)((char *)v27 + 2);
    ++a5;
    --v29;
    --v30;
  }
  while ( v30 );
  v31 = a5 - 1;
  if ( v30 )
    v31 = a5;
  v32 = v30 == 0 ? 0x8007007A : 0;
  *v31 = 0;
  v33 = -v30;
  v34 = v33 != 0 ? v32 : 0;
  if ( v34 < 0 )
  {
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::Service::WinRtHost::GetNextAppInfo",
      179,
      "failed [%#x]",
      v33 != 0 ? v32 : 0);
    v44 = wil::verify_hresult<long>((unsigned int)v34);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xB3,
      (unsigned int)"onecore\\base\\appcompat\\inventory\\service\\winrt\\lib\\winrthost.cpp",
      (const char *)v44,
      v48);
  }
  v35 = (_QWORD *)(v12 + 96);
  if ( *(_QWORD *)(v12 + 120) > 7u )
    v35 = (_QWORD *)*v35;
  do
  {
    if ( !v14 )
      break;
    if ( !*(_WORD *)v35 )
      break;
    *a6 = *(_WORD *)v35;
    v35 = (_QWORD *)((char *)v35 + 2);
    ++a6;
    --v14;
    --v15;
  }
  while ( v15 );
  v37 = a6 - 1;
  if ( v15 )
    v37 = a6;
  v38 = v15 == 0 ? 0x8007007A : 0;
  *v37 = 0;
  v39 = -v15;
  v40 = v39 != 0 ? v38 : 0;
  if ( v40 < 0 )
  {
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::Service::WinRtHost::GetNextAppInfo",
      183,
      "failed [%#x]",
      v39 != 0 ? v38 : 0);
    v45 = wil::verify_hresult<long>((unsigned int)v40);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xB7,
      (unsigned int)"onecore\\base\\appcompat\\inventory\\service\\winrt\\lib\\winrthost.cpp",
      (const char *)v45,
      v49);
  }
  return (unsigned int)v40;
}

```

## disassembly

```asm
0x1800c450c  push    rbx
0x1800c450e  push    rbp
0x1800c450f  push    rsi
0x1800c4510  push    rdi
0x1800c4511  push    r12
0x1800c4513  push    r14
0x1800c4515  push    r15
0x1800c4517  sub     rsp, 30h
0x1800c451b  mov     r14, r9
0x1800c451e  mov     rsi, r8
0x1800c4521  mov     rdi, rdx
0x1800c4524  xor     ebp, ebp
0x1800c4526  mov     r15, 0CCCCCCCCCCCCCCCDh
0x1800c4530  mov     rdx, [rdi+28h]
0x1800c4534  mov     ecx, [rdi+20h]
0x1800c4537  mov     rax, [rdx+18h]
0x1800c453b  sub     rax, [rdx+10h]
0x1800c453f  sar     rax, 5
0x1800c4543  imul    rax, r15
0x1800c4547  cmp     rcx, rax
0x1800c454a  jnb     loc_1800C4720
0x1800c4550  lea     eax, [rcx+1]
0x1800c4553  mov     [rdi+20h], eax
0x1800c4556  mov     r8, [rdx+10h]
0x1800c455a  mov     rax, [rdx+18h]
0x1800c455e  sub     rax, r8
0x1800c4561  sar     rax, 5
0x1800c4565  imul    rax, r15
0x1800c4569  cmp     rax, rcx
0x1800c456c  jbe     loc_1800C4734
0x1800c4572  lea     rbx, [rcx+rcx*4]
0x1800c4576  mov     rcx, rdi
0x1800c4579  shl     rbx, 5
0x1800c457d  add     rbx, r8
0x1800c4580  mov     rdx, rbx
0x1800c4583  call    ?AppCanBeShownToUser@WinRtHost@Service@Inventory@Compat@Windows@@CA_NAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBUWin32AppInfo@2345@@Z; Windows::Compat::Inventory::Service::WinRtHost::AppCanBeShownToUser(std::wstring &,Windows::Compat::Inventory::Service::Win32AppInfo const &)
0x1800c4588  test    al, al
0x1800c458a  jz      short loc_1800C4530
0x1800c458c  cmp     qword ptr [rbx+18h], 7
0x1800c4591  jbe     short loc_1800C4598
0x1800c4593  mov     rax, [rbx]
0x1800c4596  jmp     short loc_1800C459B
0x1800c4598  mov     rax, rbx
0x1800c459b  mov     r10d, 7FFFFFFEh
0x1800c45a1  mov     r8d, 104h
0x1800c45a7  mov     ecx, r10d
0x1800c45aa  mov     r9d, r8d
0x1800c45ad  mov     r15d, 1
0x1800c45b3  test    rcx, rcx
0x1800c45b6  jz      short loc_1800C45D3
0x1800c45b8  movzx   edx, word ptr [rax]
0x1800c45bb  test    dx, dx
0x1800c45be  jz      short loc_1800C45D3
0x1800c45c0  mov     [rsi], dx
0x1800c45c3  add     rax, 2
0x1800c45c7  add     rsi, 2
0x1800c45cb  sub     rcx, r15
0x1800c45ce  sub     r9, r15
0x1800c45d1  jnz     short loc_1800C45B3
0x1800c45d3  mov     rax, r9
0x1800c45d6  lea     rdx, [rsi-2]
0x1800c45da  neg     rax
0x1800c45dd  mov     r12d, 8007007Ah
0x1800c45e3  sbb     edi, edi
0x1800c45e5  not     edi
0x1800c45e7  and     edi, r12d
0x1800c45ea  test    r9, r9
0x1800c45ed  cmovnz  rdx, rsi
0x1800c45f1  mov     [rdx], bp
0x1800c45f4  jz      loc_1800C473A
0x1800c45fa  lea     rax, [rbx+20h]
0x1800c45fe  cmp     qword ptr [rax+18h], 7
0x1800c4603  jbe     short loc_1800C4608
0x1800c4605  mov     rax, [rax]
0x1800c4608  mov     rcx, r10
0x1800c460b  mov     r9, r8
0x1800c460e  test    rcx, rcx
0x1800c4611  jz      short loc_1800C462F
0x1800c4613  movzx   edx, word ptr [rax]
0x1800c4616  test    dx, dx
0x1800c4619  jz      short loc_1800C462F
0x1800c461b  mov     [r14], dx
0x1800c461f  add     rax, 2
0x1800c4623  add     r14, 2
0x1800c4627  sub     rcx, r15
0x1800c462a  sub     r9, r15
0x1800c462d  jnz     short loc_1800C460E
0x1800c462f  test    r9, r9
0x1800c4632  lea     rcx, [r14-2]
0x1800c4636  mov     rax, r9
0x1800c4639  cmovnz  rcx, r14
0x1800c463d  neg     rax
0x1800c4640  sbb     edx, edx
0x1800c4642  not     edx
0x1800c4644  and     edx, r12d
0x1800c4647  mov     [rcx], bp
0x1800c464a  neg     r9
0x1800c464d  sbb     edi, edi
0x1800c464f  and     edi, edx
0x1800c4651  jl      loc_1800C477A
0x1800c4657  lea     rax, [rbx+40h]
0x1800c465b  cmp     qword ptr [rax+18h], 7
0x1800c4660  jbe     short loc_1800C4665
0x1800c4662  mov     rax, [rax]
0x1800c4665  mov     rdx, [rsp+68h+arg_20]
0x1800c466d  mov     rcx, r10
0x1800c4670  mov     r9, r8
0x1800c4673  test    rcx, rcx
0x1800c4676  jz      short loc_1800C4696
0x1800c4678  movzx   r11d, word ptr [rax]
0x1800c467c  test    r11w, r11w
0x1800c4680  jz      short loc_1800C4696
0x1800c4682  mov     [rdx], r11w
0x1800c4686  add     rax, 2
0x1800c468a  add     rdx, 2
0x1800c468e  sub     rcx, r15
0x1800c4691  sub     r9, r15
0x1800c4694  jnz     short loc_1800C4673
0x1800c4696  test    r9, r9
0x1800c4699  lea     rcx, [rdx-2]
0x1800c469d  mov     rax, r9
0x1800c46a0  cmovnz  rcx, rdx
0x1800c46a4  neg     rax
0x1800c46a7  sbb     edx, edx
0x1800c46a9  not     edx
0x1800c46ab  and     edx, r12d
0x1800c46ae  mov     [rcx], bp
0x1800c46b1  neg     r9
0x1800c46b4  sbb     edi, edi
0x1800c46b6  and     edi, edx
0x1800c46b8  jl      loc_1800C47BA
0x1800c46be  lea     rax, [rbx+60h]
0x1800c46c2  cmp     qword ptr [rax+18h], 7
0x1800c46c7  jbe     short loc_1800C46CC
0x1800c46c9  mov     rax, [rax]
0x1800c46cc  mov     rdx, [rsp+68h+arg_28]
0x1800c46d4  test    r10, r10
0x1800c46d7  jz      short loc_1800C46F4
0x1800c46d9  movzx   ecx, word ptr [rax]
0x1800c46dc  test    cx, cx
0x1800c46df  jz      short loc_1800C46F4
0x1800c46e1  mov     [rdx], cx
0x1800c46e4  add     rax, 2
0x1800c46e8  add     rdx, 2
0x1800c46ec  sub     r10, r15
0x1800c46ef  sub     r8, r15
0x1800c46f2  jnz     short loc_1800C46D4
0x1800c46f4  test    r8, r8
0x1800c46f7  lea     rcx, [rdx-2]
0x1800c46fb  mov     rax, r8
0x1800c46fe  cmovnz  rcx, rdx
0x1800c4702  neg     rax
0x1800c4705  sbb     edx, edx
0x1800c4707  not     edx
0x1800c4709  and     edx, r12d
0x1800c470c  mov     [rcx], bp
0x1800c470f  neg     r8
0x1800c4712  sbb     ebx, ebx
0x1800c4714  and     ebx, edx
0x1800c4716  jl      loc_1800C47FA
0x1800c471c  mov     eax, ebx
0x1800c471e  jmp     short loc_1800C4725
0x1800c4720  mov     eax, 80070103h
0x1800c4725  add     rsp, 30h
0x1800c4729  pop     r15
0x1800c472b  pop     r14
0x1800c472d  pop     r12
0x1800c472f  pop     rdi
0x1800c4730  pop     rsi
0x1800c4731  pop     rbp
0x1800c4732  pop     rbx
0x1800c4733  retn
0x1800c4734  call    ?_Xrange@?$vector@UWin32AppInfo@Service@Inventory@Compat@Windows@@V?$allocator@UWin32AppInfo@Service@Inventory@Compat@Windows@@@std@@@std@@CAXXZ; std::vector<Windows::Compat::Inventory::Service::Win32AppInfo>::_Xrange(void)
0x1800c473a  mov     ebx, 0ABh
0x1800c473f  mov     [rsp+68h+var_48], edi; int
0x1800c4743  mov     r8d, ebx
0x1800c4746  lea     r9, aFailedX; "failed [%#x]"
0x1800c474d  lea     rdx, aWindowsCompatI_67; "Windows::Compat::Inventory::Service::Wi"...
0x1800c4754  mov     ecx, r15d
0x1800c4757  call    AslLogCallPrintf
0x1800c475c  mov     ecx, edi
0x1800c475e  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1800c4763  mov     rcx, [rsp+68h]; this
0x1800c4768  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appcompat\\inventory\\se"...
0x1800c476f  mov     r9d, eax; char *
0x1800c4772  mov     edx, ebx; void *
0x1800c4774  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800c477a  mov     ebx, 0AFh
0x1800c477f  mov     [rsp+68h+var_48], edi; int
0x1800c4783  mov     r8d, ebx
0x1800c4786  lea     r9, aFailedX; "failed [%#x]"
0x1800c478d  lea     rdx, aWindowsCompatI_67; "Windows::Compat::Inventory::Service::Wi"...
0x1800c4794  mov     ecx, r15d
0x1800c4797  call    AslLogCallPrintf
0x1800c479c  mov     ecx, edi
0x1800c479e  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1800c47a3  mov     rcx, [rsp+68h]; this
0x1800c47a8  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appcompat\\inventory\\se"...
0x1800c47af  mov     r9d, eax; char *
0x1800c47b2  mov     edx, ebx; void *
0x1800c47b4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800c47ba  mov     ebx, 0B3h
0x1800c47bf  mov     [rsp+68h+var_48], edi; int
0x1800c47c3  mov     r8d, ebx
0x1800c47c6  lea     r9, aFailedX; "failed [%#x]"
0x1800c47cd  lea     rdx, aWindowsCompatI_67; "Windows::Compat::Inventory::Service::Wi"...
0x1800c47d4  mov     ecx, r15d
0x1800c47d7  call    AslLogCallPrintf
0x1800c47dc  mov     ecx, edi
0x1800c47de  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1800c47e3  mov     rcx, [rsp+68h]; this
0x1800c47e8  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appcompat\\inventory\\se"...
0x1800c47ef  mov     r9d, eax; char *
0x1800c47f2  mov     edx, ebx; void *
0x1800c47f4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800c47fa  mov     edi, 0B7h
0x1800c47ff  mov     [rsp+68h+var_48], ebx; int
0x1800c4803  mov     r8d, edi
0x1800c4806  lea     r9, aFailedX; "failed [%#x]"
0x1800c480d  lea     rdx, aWindowsCompatI_67; "Windows::Compat::Inventory::Service::Wi"...
0x1800c4814  mov     ecx, r15d
0x1800c4817  call    AslLogCallPrintf
0x1800c481c  mov     ecx, ebx
0x1800c481e  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1800c4823  mov     rcx, [rsp+68h]; this
0x1800c4828  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appcompat\\inventory\\se"...
0x1800c482f  mov     r9d, eax; char *
0x1800c4832  mov     edx, edi; void *
0x1800c4834  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
