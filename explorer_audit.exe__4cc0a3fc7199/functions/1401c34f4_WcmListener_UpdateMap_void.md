# WcmListener::_UpdateMap(void)

- ea: `0x1401c34f4`
- end: `0x1401c39f6`
- name: `?_UpdateMap@WcmListener@@IEAAXXZ`
- size: `1282`
- prototype: `void __fastcall(WcmListener *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1401c1900`

## callees

- `0x140061db0`
- `0x140066128`
- `0x1401040e0`
- `0x140104ce0`
- `0x140130ff4`
- `0x1401b21e8`
- `0x1401b2398`
- `0x1401c1d88`
- `0x1401c34f4`
- `0x1401c39fc`
- `0x1401c4088`
- `0x1401c41c0`
- `0x1401c442c`
- `0x1401c4634`

## import_xrefs

- `ntdll!NtQueryWnfStateData` at `0x1401c35a0`
- `ntdll!NtQueryWnfStateData` at `0x1401c363d`
- `ntdll!NtQueryWnfStateData` at `0x1401c37be`
- `ntdll!NtQueryWnfStateData` at `0x1401c35a0`
- `ntdll!NtQueryWnfStateData` at `0x1401c363d`
- `ntdll!NtQueryWnfStateData` at `0x1401c37be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1401c39cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1401c39cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1401c35f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1401c35f7`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall WcmListener::_UpdateMap(WcmListener *this)
{
  unsigned int *v2; // rbx
  unsigned int WnfStateData; // eax
  __int64 v4; // rdx
  __int64 v5; // r8
  unsigned int v6; // edi
  PVOID *v7; // r10
  unsigned int *v8; // rax
  int v9; // eax
  PVOID *v10; // rcx
  unsigned int v11; // r12d
  __int64 v12; // r15
  __int64 v13; // rdi
  unsigned int *v14; // r13
  int v15; // r14d
  __int64 *v16; // rax
  __int64 v17; // rdx
  _BYTE *v18; // [rsp+20h] [rbp-E0h]
  SIZE_T *v19; // [rsp+28h] [rbp-D8h]
  __int64 v20; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v21[2]; // [rsp+48h] [rbp-B8h] BYREF
  char v22[8]; // [rsp+58h] [rbp-A8h] BYREF
  SIZE_T cb[2]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v24[608]; // [rsp+70h] [rbp-90h] BYREF

  cb[0] = 0;
  v2 = 0;
  v21[0] = 0;
  wil::EnterCriticalSection(v21, (char *)this + 144);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, &WPP_606eaee946af3fb1432a211036cbf184_Traceguids);
  WnfStateData = NtQueryWnfStateData(&WNF_WCM_INTERFACE_LIST, 0, 0, (char *)cb + 4);
  v6 = WnfStateData;
  v7 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_dD(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, LODWORD(cb[0]), WnfStateData, LODWORD(cb[0]), cb);
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v6 == -1073741789 && LODWORD(cb[0]) >= 0x3C )
  {
    v8 = (unsigned int *)CoTaskMemAlloc(LODWORD(cb[0]));
    v2 = v8;
    v21[1] = v8;
    if ( v8 )
    {
      memset_0(v8, 0, LODWORD(cb[0]));
      v19 = cb;
      HIDWORD(v18) = HIDWORD(v2);
      v9 = NtQueryWnfStateData(&WNF_WCM_INTERFACE_LIST, 0, 0, (char *)cb + 4);
      v5 = LODWORD(cb[0]);
      if ( v9 >= 0 && LODWORD(cb[0]) >= 0x3C )
      {
        v10 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          {
            LODWORD(v18) = cb[0];
            WPP_SF_dD(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, LODWORD(cb[0]), (unsigned int)v9, v18, cb);
            v10 = (PVOID *)WPP_GLOBAL_Control;
          }
          if ( v10 != &WPP_GLOBAL_Control )
          {
            if ( (*((_BYTE *)v10 + 28) & 4) != 0 )
            {
              WPP_SF__guid_(v10[2], 42, &WPP_606eaee946af3fb1432a211036cbf184_Traceguids, v2);
              v10 = (PVOID *)WPP_GLOBAL_Control;
            }
            if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 4) != 0 )
            {
              LODWORD(v19) = v2[6];
              LODWORD(v18) = v2[5];
              WPP_SF_LLLL(v10[2], 43, v5, v2[4], v18, v19, v2[7]);
            }
          }
        }
        *(_OWORD *)((char *)this + 236) = *((_OWORD *)v2 + 1);
        *(_OWORD *)((char *)this + 252) = *(_OWORD *)v2;
        v11 = v2[8];
        v7 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          LODWORD(v18) = *((_DWORD *)this + 48);
          WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, &WPP_606eaee946af3fb1432a211036cbf184_Traceguids, v11, v18);
          v7 = (PVOID *)WPP_GLOBAL_Control;
        }
        v12 = 0;
        if ( v11 )
        {
          while ( 1 )
          {
            v13 = (__int64)&v2[6 * v12 + 9];
            if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 4) != 0 )
            {
              LODWORD(v19) = *(_DWORD *)(v13 + 20);
              LODWORD(v18) = *(_DWORD *)(v13 + 16);
              WPP_SF__guid_DD(v7[2], 45, v5, &v2[6 * v12 + 9], v18, v19);
            }
            memset_0(v24, 0, 0x25Cu);
            LODWORD(cb[0]) = 604;
            v14 = &v2[6 * v12];
            v19 = cb;
            v18 = v24;
            v15 = NtQueryWnfStateData(v14 + 13, 0, 0, (char *)cb + 4);
            v7 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            {
              LODWORD(v18) = cb[0];
              WPP_SF_dD(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, v5, (unsigned int)v15, v18, cb);
              v7 = (PVOID *)WPP_GLOBAL_Control;
            }
            if ( v15 < 0 || LODWORD(cb[0]) < 0x25C )
            {
              if ( v7 == &WPP_GLOBAL_Control || (*((_BYTE *)v7 + 28) & 1) == 0 )
                goto LABEL_48;
              WPP_SF_(v7[2], 49, &WPP_606eaee946af3fb1432a211036cbf184_Traceguids);
              goto LABEL_47;
            }
            v20 = 0;
            std::_Tree<std::_Tmap_traits<_GUID,INTERFACE_PROPERTIES,std::less<_GUID>,std::allocator<std::pair<_GUID const,INTERFACE_PROPERTIES>>,0>>::find(
              (char *)this + 184,
              &v20,
              &v2[6 * v12 + 9]);
            v4 = v20;
            if ( v20 != *((_QWORD *)this + 23) )
              break;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
              WPP_SF__guid_(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                47,
                &WPP_606eaee946af3fb1432a211036cbf184_Traceguids,
                &v2[6 * v12 + 9]);
            if ( (int)WcmListener::_AddNetworkInterfaceMapEntry(
                        this,
                        (const struct _GUID *)&v2[6 * v12 + 9],
                        *(struct _WNF_STATE_NAME *)(v14 + 13)) < 0 )
            {
              v7 = (PVOID *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                goto LABEL_48;
              WPP_SF__guid_(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                48,
                &WPP_606eaee946af3fb1432a211036cbf184_Traceguids,
                &v2[6 * v12 + 9]);
            }
            else
            {
              v16 = (__int64 *)std::_Tree<std::_Tmap_traits<_GUID,INTERFACE_PROPERTIES,std::less<_GUID>,std::allocator<std::pair<_GUID const,INTERFACE_PROPERTIES>>,0>>::find(
                                 (char *)this + 184,
                                 v22,
                                 &v2[6 * v12 + 9]);
              v4 = *v16;
              if ( *v16 != *((_QWORD *)this + 23) )
                break;
            }
LABEL_47:
            v7 = (PVOID *)WPP_GLOBAL_Control;
LABEL_48:
            v12 = (unsigned int)(v12 + 1);
            if ( (unsigned int)v12 >= v11 )
              goto LABEL_61;
          }
          WcmListener::_UpdateNetworkInterfaceMapEntry(this, v4, v24);
          goto LABEL_47;
        }
        goto LABEL_61;
      }
      v7 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_64;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_61;
      LODWORD(v18) = cb[0];
      WPP_SF_dD(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, LODWORD(cb[0]), (unsigned int)v9, v18, cb);
      goto LABEL_60;
    }
    v7 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_64;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_61;
    v17 = 51;
LABEL_59:
    WPP_SF_(v7[2], v17, &WPP_606eaee946af3fb1432a211036cbf184_Traceguids);
LABEL_60:
    v7 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_61;
  }
  if ( v7 == &WPP_GLOBAL_Control )
    goto LABEL_64;
  if ( (*((_BYTE *)v7 + 28) & 1) != 0 )
  {
    v17 = 52;
    goto LABEL_59;
  }
LABEL_61:
  if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 4) != 0 )
    WPP_SF_(v7[2], 53, &WPP_606eaee946af3fb1432a211036cbf184_Traceguids);
LABEL_64:
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(
    v21,
    v4,
    v5);
  if ( v2 )
    CoTaskMemFree(v2);
}

```

## disassembly

```asm
0x1401c34f4  push    rbp
0x1401c34f6  push    rbx
0x1401c34f7  push    rsi
0x1401c34f8  push    rdi
0x1401c34f9  push    r12
0x1401c34fb  push    r13
0x1401c34fd  push    r14
0x1401c34ff  push    r15
0x1401c3501  lea     rbp, [rsp-1E8h]
0x1401c3509  sub     rsp, 2E8h
0x1401c3510  mov     rax, cs:__security_cookie
0x1401c3517  xor     rax, rsp
0x1401c351a  mov     [rbp+220h+var_50], rax
0x1401c3521  mov     rsi, rcx
0x1401c3524  mov     dword ptr [rsp+320h+cb+4], 0
0x1401c352c  mov     dword ptr [rsp+320h+cb], 0
0x1401c3534  xor     ebx, ebx
0x1401c3536  mov     [rsp+320h+var_2D8], rbx
0x1401c353b  lea     rdx, [rcx+90h]
0x1401c3542  lea     rcx, [rsp+320h+var_2D8]
0x1401c3547  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x1401c354c  nop
0x1401c354d  lea     r13, WPP_GLOBAL_Control
0x1401c3554  mov     r14b, 4
0x1401c3557  mov     rcx, cs:WPP_GLOBAL_Control
0x1401c355e  cmp     rcx, r13
0x1401c3561  jz      short loc_1401C357C
0x1401c3563  test    [rcx+1Ch], r14b
0x1401c3567  jz      short loc_1401C357C
0x1401c3569  lea     edx, [rbx+27h]
0x1401c356c  lea     r8, WPP_606eaee946af3fb1432a211036cbf184_Traceguids
0x1401c3573  mov     rcx, [rcx+10h]
0x1401c3577  call    WPP_SF_
0x1401c357c  lea     rax, [rsp+320h+cb]
0x1401c3581  mov     [rsp+320h+var_2F8], rax
0x1401c3586  mov     [rsp+320h+var_300], 0
0x1401c358f  lea     r9, [rsp+320h+cb+4]
0x1401c3594  xor     r8d, r8d
0x1401c3597  xor     edx, edx
0x1401c3599  lea     rcx, WNF_WCM_INTERFACE_LIST
0x1401c35a0  call    cs:__imp_NtQueryWnfStateData
0x1401c35a6  mov     edi, eax
0x1401c35a8  mov     r10, cs:WPP_GLOBAL_Control
0x1401c35af  cmp     r10, r13
0x1401c35b2  jz      short loc_1401C35DC
0x1401c35b4  test    [r10+1Ch], r14b
0x1401c35b8  jz      short loc_1401C35DC
0x1401c35ba  mov     edx, 28h ; '('
0x1401c35bf  mov     r8d, dword ptr [rsp+320h+cb]
0x1401c35c4  mov     dword ptr [rsp+320h+var_300], r8d
0x1401c35c9  mov     r9d, eax
0x1401c35cc  mov     rcx, [r10+10h]
0x1401c35d0  call    WPP_SF_dD
0x1401c35d5  mov     r10, cs:WPP_GLOBAL_Control
0x1401c35dc  cmp     edi, 0C0000023h
0x1401c35e2  jnz     loc_1401C3971
0x1401c35e8  cmp     dword ptr [rsp+320h+cb], 3Ch ; '<'
0x1401c35ed  jb      loc_1401C3971
0x1401c35f3  mov     ecx, dword ptr [rsp+320h+cb]; cb
0x1401c35f7  call    cs:__imp_CoTaskMemAlloc
0x1401c35fd  mov     rbx, rax
0x1401c3600  mov     [rsp+320h+var_2D0], rax
0x1401c3605  test    rax, rax
0x1401c3608  jz      loc_1401C3957
0x1401c360e  mov     r8d, dword ptr [rsp+320h+cb]; Size
0x1401c3613  xor     edx, edx; Val
0x1401c3615  mov     rcx, rax; void *
0x1401c3618  call    memset_0
0x1401c361d  lea     rax, [rsp+320h+cb]
0x1401c3622  mov     [rsp+320h+var_2F8], rax
0x1401c3627  mov     [rsp+320h+var_300], rbx
0x1401c362c  lea     r9, [rsp+320h+cb+4]
0x1401c3631  xor     r8d, r8d
0x1401c3634  xor     edx, edx
0x1401c3636  lea     rcx, WNF_WCM_INTERFACE_LIST
0x1401c363d  call    cs:__imp_NtQueryWnfStateData
0x1401c3643  mov     r8d, dword ptr [rsp+320h+cb]
0x1401c3648  test    eax, eax
0x1401c364a  js      loc_1401C3928
0x1401c3650  cmp     r8d, 3Ch ; '<'
0x1401c3654  jb      loc_1401C3928
0x1401c365a  mov     rcx, cs:WPP_GLOBAL_Control
0x1401c3661  cmp     rcx, r13
0x1401c3664  jz      short loc_1401C36E5
0x1401c3666  test    [rcx+1Ch], r14b
0x1401c366a  jz      short loc_1401C3689
0x1401c366c  mov     edx, 29h ; ')'
0x1401c3671  mov     dword ptr [rsp+320h+var_300], r8d
0x1401c3676  mov     r9d, eax
0x1401c3679  mov     rcx, [rcx+10h]
0x1401c367d  call    WPP_SF_dD
0x1401c3682  mov     rcx, cs:WPP_GLOBAL_Control
0x1401c3689  cmp     rcx, r13
0x1401c368c  jz      short loc_1401C36E5
0x1401c368e  test    [rcx+1Ch], r14b
0x1401c3692  jz      short loc_1401C36B3
0x1401c3694  mov     edx, 2Ah ; '*'
0x1401c3699  mov     r9, rbx
0x1401c369c  lea     r8, WPP_606eaee946af3fb1432a211036cbf184_Traceguids
0x1401c36a3  mov     rcx, [rcx+10h]
0x1401c36a7  call    WPP_SF__guid_
0x1401c36ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1401c36b3  cmp     rcx, r13
0x1401c36b6  jz      short loc_1401C36E5
0x1401c36b8  test    [rcx+1Ch], r14b
0x1401c36bc  jz      short loc_1401C36E5
0x1401c36be  mov     edx, 2Bh ; '+'
0x1401c36c3  mov     eax, [rbx+1Ch]
0x1401c36c6  mov     [rsp+320h+var_2F0], eax
0x1401c36ca  mov     eax, [rbx+18h]
0x1401c36cd  mov     dword ptr [rsp+320h+var_2F8], eax
0x1401c36d1  mov     eax, [rbx+14h]
0x1401c36d4  mov     dword ptr [rsp+320h+var_300], eax
0x1401c36d8  mov     r9d, [rbx+10h]
0x1401c36dc  mov     rcx, [rcx+10h]
0x1401c36e0  call    WPP_SF_LLLL
0x1401c36e5  movups  xmm0, xmmword ptr [rbx+10h]
0x1401c36e9  movdqu  xmmword ptr [rsi+0ECh], xmm0
0x1401c36f1  movups  xmm1, xmmword ptr [rbx]
0x1401c36f4  movdqu  xmmword ptr [rsi+0FCh], xmm1
0x1401c36fc  mov     r12d, [rbx+20h]
0x1401c3700  mov     r10, cs:WPP_GLOBAL_Control
0x1401c3707  cmp     r10, r13
0x1401c370a  jz      short loc_1401C373B
0x1401c370c  test    [r10+1Ch], r14b
0x1401c3710  jz      short loc_1401C373B
0x1401c3712  mov     edx, 2Ch ; ','
0x1401c3717  mov     eax, [rsi+0C0h]
0x1401c371d  mov     dword ptr [rsp+320h+var_300], eax
0x1401c3721  mov     r9d, r12d
0x1401c3724  lea     r8, WPP_606eaee946af3fb1432a211036cbf184_Traceguids
0x1401c372b  mov     rcx, [r10+10h]
0x1401c372f  call    WPP_SF_dd
0x1401c3734  mov     r10, cs:WPP_GLOBAL_Control
0x1401c373b  xor     r15d, r15d
0x1401c373e  test    r12d, r12d
0x1401c3741  jz      loc_1401C3999
0x1401c3747  lea     r14, [r15+r15*2]
0x1401c374b  lea     rdi, [rbx+24h]
0x1401c374f  lea     rdi, [rdi+r14*8]
0x1401c3753  cmp     r10, r13
0x1401c3756  jz      short loc_1401C377E
0x1401c3758  test    byte ptr [r10+1Ch], 4
0x1401c375d  jz      short loc_1401C377E
0x1401c375f  mov     edx, 2Dh ; '-'
0x1401c3764  mov     eax, [rdi+14h]
0x1401c3767  mov     dword ptr [rsp+320h+var_2F8], eax
0x1401c376b  mov     eax, [rdi+10h]
0x1401c376e  mov     dword ptr [rsp+320h+var_300], eax
0x1401c3772  mov     r9, rdi
0x1401c3775  mov     rcx, [r10+10h]
0x1401c3779  call    WPP_SF__guid_DD
0x1401c377e  mov     r13d, 25Ch
0x1401c3784  mov     r8d, r13d; Size
0x1401c3787  xor     edx, edx; Val
0x1401c3789  lea     rcx, [rsp+320h+var_2B0]; void *
0x1401c378e  call    memset_0
0x1401c3793  mov     dword ptr [rsp+320h+cb], r13d
0x1401c3798  lea     r13, [rbx+r14*8]
0x1401c379c  lea     rax, [rsp+320h+cb]
0x1401c37a1  mov     [rsp+320h+var_2F8], rax
0x1401c37a6  lea     rax, [rsp+320h+var_2B0]
0x1401c37ab  mov     [rsp+320h+var_300], rax
0x1401c37b0  lea     r9, [rsp+320h+cb+4]
0x1401c37b5  xor     r8d, r8d
0x1401c37b8  xor     edx, edx
0x1401c37ba  lea     rcx, [r13+34h]
0x1401c37be  call    cs:__imp_NtQueryWnfStateData
0x1401c37c4  mov     r14d, eax
0x1401c37c7  mov     r10, cs:WPP_GLOBAL_Control
0x1401c37ce  lea     rax, WPP_GLOBAL_Control
0x1401c37d5  cmp     r10, rax
0x1401c37d8  jz      short loc_1401C3801
0x1401c37da  test    byte ptr [r10+1Ch], 4
0x1401c37df  jz      short loc_1401C3801
0x1401c37e1  mov     edx, 2Eh ; '.'
0x1401c37e6  mov     ecx, dword ptr [rsp+320h+cb]
0x1401c37ea  mov     dword ptr [rsp+320h+var_300], ecx
0x1401c37ee  mov     r9d, r14d
0x1401c37f1  mov     rcx, [r10+10h]
0x1401c37f5  call    WPP_SF_dD
0x1401c37fa  mov     r10, cs:WPP_GLOBAL_Control
0x1401c3801  test    r14d, r14d
0x1401c3804  js      loc_1401C38E8
0x1401c380a  cmp     dword ptr [rsp+320h+cb], 25Ch
0x1401c3812  jb      loc_1401C38E8
0x1401c3818  mov     [rsp+320h+var_2E0], 0
0x1401c3821  lea     r14, [rsi+0B8h]
0x1401c3828  mov     r8, rdi
0x1401c382b  lea     rdx, [rsp+320h+var_2E0]
0x1401c3830  mov     rcx, r14
0x1401c3833  call    ?find@?$_Tree@V?$_Tmap_traits@U_GUID@@UINTERFACE_PROPERTIES@@U?$less@U_GUID@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@UINTERFACE_PROPERTIES@@@std@@@4@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@UINTERFACE_PROPERTIES@@@std@@@std@@@std@@@2@AEBU_GUID@@@Z; std::_Tree<std::_Tmap_traits<_GUID,INTERFACE_PROPERTIES,std::less<_GUID>,std::allocator<std::pair<_GUID const,INTERFACE_PROPERTIES>>,0>>::find(_GUID const &)
0x1401c3838  mov     rdx, [rsp+320h+var_2E0]
0x1401c383d  cmp     rdx, [r14]
0x1401c3840  jnz     short loc_1401C389E
0x1401c3842  mov     rcx, cs:WPP_GLOBAL_Control
0x1401c3849  lea     rax, WPP_GLOBAL_Control
0x1401c3850  cmp     rcx, rax
0x1401c3853  jz      short loc_1401C3873
0x1401c3855  test    byte ptr [rcx+1Ch], 4
0x1401c3859  jz      short loc_1401C3873
0x1401c385b  mov     edx, 2Fh ; '/'
0x1401c3860  mov     r9, rdi
0x1401c3863  lea     r8, WPP_606eaee946af3fb1432a211036cbf184_Traceguids
0x1401c386a  mov     rcx, [rcx+10h]
0x1401c386e  call    WPP_SF__guid_
0x1401c3873  mov     r8, [r13+34h]; struct _WNF_STATE_NAME
0x1401c3877  mov     rdx, rdi; struct _GUID *
0x1401c387a  mov     rcx, rsi; this
0x1401c387d  call    ?_AddNetworkInterfaceMapEntry@WcmListener@@IEAAJAEBU_GUID@@U_WNF_STATE_NAME@@@Z; WcmListener::_AddNetworkInterfaceMapEntry(_GUID const &,_WNF_STATE_NAME)
0x1401c3882  test    eax, eax
0x1401c3884  js      short loc_1401C38B4
0x1401c3886  mov     r8, rdi
0x1401c3889  lea     rdx, [rsp+320h+var_2C8]
0x1401c388e  mov     rcx, r14
0x1401c3891  call    ?find@?$_Tree@V?$_Tmap_traits@U_GUID@@UINTERFACE_PROPERTIES@@U?$less@U_GUID@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@UINTERFACE_PROPERTIES@@@std@@@4@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@UINTERFACE_PROPERTIES@@@std@@@std@@@std@@@2@AEBU_GUID@@@Z; std::_Tree<std::_Tmap_traits<_GUID,INTERFACE_PROPERTIES,std::less<_GUID>,std::allocator<std::pair<_GUID const,INTERFACE_PROPERTIES>>,0>>::find(_GUID const &)
0x1401c3896  mov     rdx, [rax]
0x1401c3899  cmp     rdx, [r14]
0x1401c389c  jz      short loc_1401C38AB
0x1401c389e  lea     r8, [rsp+320h+var_2B0]
0x1401c38a3  mov     rcx, rsi
0x1401c38a6  call    ?_UpdateNetworkInterfaceMapEntry@WcmListener@@IEAAXV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@UINTERFACE_PROPERTIES@@@std@@@std@@@std@@@std@@PEAU_WCM_WNF_INTERFACE_STATE@@@Z; WcmListener::_UpdateNetworkInterfaceMapEntry(std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,INTERFACE_PROPERTIES>>>>,_WCM_WNF_INTERFACE_STATE *)
0x1401c38ab  lea     r13, WPP_GLOBAL_Control
0x1401c38b2  jmp     short loc_1401C3910
0x1401c38b4  mov     r10, cs:WPP_GLOBAL_Control
0x1401c38bb  lea     r13, WPP_GLOBAL_Control
0x1401c38c2  cmp     r10, r13
0x1401c38c5  jz      short loc_1401C3917
0x1401c38c7  test    byte ptr [r10+1Ch], 1
0x1401c38cc  jz      short loc_1401C3917
0x1401c38ce  mov     edx, 30h ; '0'
0x1401c38d3  mov     r9, rdi
0x1401c38d6  lea     r8, WPP_606eaee946af3fb1432a211036cbf184_Traceguids
0x1401c38dd  mov     rcx, [r10+10h]
0x1401c38e1  call    WPP_SF__guid_
0x1401c38e6  jmp     short loc_1401C3910
0x1401c38e8  lea     r13, WPP_GLOBAL_Control
0x1401c38ef  cmp     r10, r13
0x1401c38f2  jz      short loc_1401C3917
0x1401c38f4  test    byte ptr [r10+1Ch], 1
0x1401c38f9  jz      short loc_1401C3917
0x1401c38fb  mov     edx, 31h ; '1'
0x1401c3900  lea     r8, WPP_606eaee946af3fb1432a211036cbf184_Traceguids
0x1401c3907  mov     rcx, [r10+10h]
0x1401c390b  call    WPP_SF_
0x1401c3910  mov     r10, cs:WPP_GLOBAL_Control
0x1401c3917  inc     r15d
0x1401c391a  cmp     r15d, r12d
0x1401c391d  jb      loc_1401C3747
0x1401c3923  mov     r14b, 4
0x1401c3926  jmp     short loc_1401C3999
0x1401c3928  mov     r10, cs:WPP_GLOBAL_Control
0x1401c392f  cmp     r10, r13
0x1401c3932  jz      loc_1401C39BA
0x1401c3938  test    byte ptr [r10+1Ch], 1
0x1401c393d  jz      short loc_1401C3999
0x1401c393f  mov     edx, 32h ; '2'
0x1401c3944  mov     dword ptr [rsp+320h+var_300], r8d
0x1401c3949  mov     r9d, eax
0x1401c394c  mov     rcx, [r10+10h]
0x1401c3950  call    WPP_SF_dD
0x1401c3955  jmp     short loc_1401C3992
0x1401c3957  mov     r10, cs:WPP_GLOBAL_Control
0x1401c395e  cmp     r10, r13
0x1401c3961  jz      short loc_1401C39BA
0x1401c3963  test    byte ptr [r10+1Ch], 1
0x1401c3968  jz      short loc_1401C3999
0x1401c396a  mov     edx, 33h ; '3'
0x1401c396f  jmp     short loc_1401C3982
0x1401c3971  cmp     r10, r13
0x1401c3974  jz      short loc_1401C39BA
0x1401c3976  test    byte ptr [r10+1Ch], 1
0x1401c397b  jz      short loc_1401C3999
0x1401c397d  mov     edx, 34h ; '4'
0x1401c3982  lea     r8, WPP_606eaee946af3fb1432a211036cbf184_Traceguids
0x1401c3989  mov     rcx, [r10+10h]
0x1401c398d  call    WPP_SF_
0x1401c3992  mov     r10, cs:WPP_GLOBAL_Control
0x1401c3999  cmp     r10, r13
0x1401c399c  jz      short loc_1401C39BA
0x1401c399e  test    [r10+1Ch], r14b
0x1401c39a2  jz      short loc_1401C39BA
0x1401c39a4  mov     edx, 35h ; '5'
0x1401c39a9  lea     r8, WPP_606eaee946af3fb1432a211036cbf184_Traceguids
0x1401c39b0  mov     rcx, [r10+10h]
0x1401c39b4  call    WPP_SF_
0x1401c39b9  nop
0x1401c39ba  lea     rcx, [rsp+320h+var_2D8]
0x1401c39bf  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(void)
0x1401c39c4  nop
0x1401c39c5  test    rbx, rbx
0x1401c39c8  jz      short loc_1401C39D3
0x1401c39ca  mov     rcx, rbx; pv
0x1401c39cd  call    cs:__imp_CoTaskMemFree
0x1401c39d3  mov     rcx, [rbp+220h+var_50]
0x1401c39da  xor     rcx, rsp; StackCookie
0x1401c39dd  call    __security_check_cookie
0x1401c39e2  add     rsp, 2E8h
0x1401c39e9  pop     r15
0x1401c39eb  pop     r14
  ... truncated ...
```
