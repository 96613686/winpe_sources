# FileDialogProc(HWND__ *,uint,unsigned __int64,__int64,__int64)

- ea: `0x14002e450`
- end: `0x14002ea06`
- name: `?FileDialogProc@@YAJPEAUHWND__@@I_K_J2@Z`
- size: `1462`
- prototype: `__int64 __usercall@<rax>(HWND@<rcx>, unsigned int@<edx>, unsigned __int64@<r8>, __int64@<r9>, __int64)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callees

- `0x140001cc4`
- `0x140002463`
- `0x1400044f8`
- `0x1400080fc`
- `0x14000aa78`
- `0x14002c0a4`
- `0x14002e450`
- `0x140044398`
- `0x140044508`
- `0x140047a04`
- `0x14004ad80`

## import_xrefs

- `ADVAPI32!EventWrite` at `0x14002e537`
- `ADVAPI32!EventWrite` at `0x14002e537`
- `KERNEL32!GetModuleHandleW` at `0x14002e5e0`
- `KERNEL32!GetModuleHandleW` at `0x14002e5e0`
- `KERNEL32!WaitForSingleObject` at `0x14002e58f`
- `KERNEL32!WaitForSingleObject` at `0x14002e58f`
- `USER32!SendMessageW` at `0x14002e6ec`
- `USER32!SendMessageW` at `0x14002e6ec`
- `USER32!LoadStringW` at `0x14002e5fe`
- `USER32!LoadStringW` at `0x14002e5fe`
- `USER32!PostMessageW` at `0x14002e761`
- `USER32!PostMessageW` at `0x14002e761`
- `msvcrt!??3@YAXPEAX@Z` at `0x14002e863`
- `msvcrt!??3@YAXPEAX@Z` at `0x14002e975`
- `msvcrt!??3@YAXPEAX@Z` at `0x14002e9a2`
- `msvcrt!??3@YAXPEAX@Z` at `0x14002e863`
- `msvcrt!??3@YAXPEAX@Z` at `0x14002e975`
- `msvcrt!??3@YAXPEAX@Z` at `0x14002e9a2`
- `OLEAUT32!__imp_SysAllocString` at `0x14002e653`
- `OLEAUT32!__imp_SysAllocString` at `0x14002e653`
- `OLEAUT32!__imp_SysFreeString` at `0x14002e686`
- `OLEAUT32!__imp_SysFreeString` at `0x14002e686`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall FileDialogProc(HWND a1, int a2, __int64 a3, __int64 a4, __int64 a5)
{
  __int64 v7; // rdx
  const unsigned __int16 *v8; // rax
  int v9; // ebx
  int v10; // ebx
  CEventLogger *v11; // rax
  DWORD v12; // eax
  CEventLogger *v13; // r8
  HMODULE ModuleHandleW; // rax
  CEventLogger *v15; // rsi
  BSTR v16; // rax
  OLECHAR *v17; // rbx
  __int64 v18; // rax
  CEventLogger *v19; // r8
  __int64 v20; // rsi
  __int64 v21; // rax
  _QWORD *v22; // rdi
  __int64 v23; // r14
  __int64 i; // rbx
  __int64 v25; // rdx
  _QWORD *j; // rax
  __int64 v27; // rcx
  int v28; // edx
  void *v29; // rcx
  _QWORD *v30; // rax
  _QWORD *v31; // rcx
  CEventLogger *v32; // r9
  __int64 v33; // rax
  _BYTE *v34; // rdx
  __int64 v35; // rdx
  _BYTE *v36; // rax
  CEventLogger *v37; // rax
  enum __MIDL___MIDL_itf_rdpencomapi_0000_0000_0003 v39; // [rsp+20h] [rbp-E0h]
  int v40; // [rsp+30h] [rbp-D0h] BYREF
  BSTR v41; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v42; // [rsp+40h] [rbp-C0h]
  _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-B0h] BYREF
  int *v44; // [rsp+60h] [rbp-A0h]
  __int64 v45; // [rsp+68h] [rbp-98h]
  BSTR *v46; // [rsp+70h] [rbp-90h]
  __int64 v47; // [rsp+78h] [rbp-88h]
  WCHAR Buffer[256]; // [rsp+80h] [rbp-80h] BYREF
  OLECHAR psz[1024]; // [rsp+280h] [rbp+180h] BYREF

  memset_0(psz, 0, sizeof(psz));
  memset_0(Buffer, 0, sizeof(Buffer));
  DWORD1(v42) = 0;
  LODWORD(v41) = a2;
  v40 = 130;
  v7 = 0x7FFFFFFF;
  v8 = L"base\\diagnosis\\ra\\ui\\filexfer.cpp";
  do
  {
    if ( !*v8 )
      break;
    ++v8;
    --v7;
  }
  while ( v7 );
  if ( v7 )
  {
    UserData.Ptr = (ULONGLONG)L"base\\diagnosis\\ra\\ui\\filexfer.cpp";
    UserData.Size = v7 != 0 ? -2 - 2 * v7 + 2 : 2;
    UserData.Reserved = 0;
    v44 = &v40;
    v45 = 4;
    v46 = &v41;
    v47 = 4;
    EventWrite(g_Logger, &Switch_On, 3u, &UserData);
  }
  if ( !a2 )
  {
    v19 = _AtlModule;
    *((_DWORD *)_AtlModule + 138) |= 4u;
    *((_QWORD *)v19 + 116) = a1;
    *((_QWORD *)v19 + 118) = 0;
    if ( a5 == 1 )
    {
      v29 = (void *)*((_QWORD *)v19 + 113);
      if ( v29 )
      {
        operator delete(v29);
        v19 = _AtlModule;
        *((_QWORD *)_AtlModule + 113) = 0;
      }
      *((_DWORD *)v19 + 228) = 13;
      v30 = operator new(0x50u, (const struct std::nothrow_t *)&std::nothrow);
      v31 = v30;
      v41 = (BSTR)v30;
      v32 = _AtlModule;
      if ( v30 )
      {
        v30[7] = *((_QWORD *)_AtlModule + 104);
        v30[8] = 0;
        v30[9] = 0;
        v33 = 16;
        v34 = v31;
        do
        {
          *v34++ = 0;
          --v33;
        }
        while ( v33 );
        v35 = 40;
        v36 = v31 + 2;
        do
        {
          *v36++ = 0;
          --v35;
        }
        while ( v35 );
      }
      else
      {
        v31 = 0;
      }
      *((_QWORD *)v32 + 113) = v31;
      if ( !v31 )
      {
        *((_DWORD *)v32 + 228) = 14;
        return 0;
      }
      *((_QWORD *)&v42 + 1) = &SendFileClientCallback;
      LODWORD(v42) = 180000;
      if ( !*(_DWORD *)(v31[7] + 460LL) )
      {
        operator delete(v31);
        v11 = _AtlModule;
        *((_QWORD *)_AtlModule + 113) = 0;
        goto LABEL_11;
      }
      *(_OWORD *)v31 = v42;
      v31[5] = v31;
      *((_QWORD *)v32 + 116) = a1;
      if ( (int)RAFileXferClient::SendFile(
                  *((RAFileXferClient **)v32 + 113),
                  -(*(_QWORD *)(*((_QWORD *)v32 + 104) + 208LL) != 0),
                  *((const unsigned __int16 **)v32 + 115),
                  (unsigned int)v32,
                  v39) < 0 )
      {
        operator delete(*((void **)_AtlModule + 113));
        v37 = _AtlModule;
        *((_QWORD *)_AtlModule + 113) = 0;
        *((_DWORD *)v37 + 228) = 14;
        *((_QWORD *)v37 + 116) = 0;
      }
      return 0;
    }
    v28 = 5;
LABEL_64:
    CSessionLogger::WriteToLog((int *)v19 + 182, v28, *((_QWORD *)v19 + 115));
    return 0;
  }
  v9 = a2 - 2;
  if ( !v9 )
  {
    v19 = _AtlModule;
    if ( *((_DWORD *)_AtlModule + 228) != 13 )
      return 0;
    if ( a5 == 1 )
    {
      RAFileXferClient::Cancel(*((RAFileXferClient **)_AtlModule + 113));
    }
    else
    {
      v20 = *((_QWORD *)_AtlModule + 112);
      v21 = *(_QWORD *)(v20 + 8);
      if ( !*(_DWORD *)(v21 + 460) )
        goto LABEL_46;
      v22 = *(_QWORD **)(v21 + 480);
      if ( !v22 )
        goto LABEL_46;
      v23 = *(_QWORD *)(v21 + 512);
      if ( !v23 )
        goto LABEL_46;
      for ( i = 0; i != 10; ++i )
      {
        v25 = v23 + 56 * i;
        if ( *(_DWORD *)v25 != -1000 && *(_DWORD *)(v25 + 32) <= 1u )
        {
          for ( j = (_QWORD *)*v22; j != v22; j = (_QWORD *)*j )
          {
            v27 = j[2];
            if ( v27 != *(_QWORD *)v20 && v27 && *(_DWORD *)(v27 + 16) == -100 )
              goto LABEL_44;
          }
          AbortReceiver(*(struct CRATicket **)(v20 + 8), (struct RECV_ENTRY *)v25, 1);
        }
LABEL_44:
        ;
      }
    }
    v19 = _AtlModule;
LABEL_46:
    v28 = 7;
    goto LABEL_64;
  }
  v10 = v9 - 2;
  if ( !v10 )
  {
    v12 = WaitForSingleObject(*((HANDLE *)_AtlModule + 106), 0);
    v13 = _AtlModule;
    if ( !v12 )
      *((_DWORD *)_AtlModule + 228) = 8;
    switch ( *((_DWORD *)v13 + 228) )
    {
      case 7:
        *((_DWORD *)v13 + 228) = 13;
        ShowErrorMessage(0x20Fu, 0x286u, a1, 0, (unsigned __int16 *)0xFFFE, 0);
        break;
      case 8:
        CSessionLogger::WriteToLog((int *)v13 + 182, 7, *((_QWORD *)v13 + 115));
        *((_DWORD *)_AtlModule + 228) = 14;
        break;
      case 0xD:
        v18 = 100LL * *((_QWORD *)v13 + 118) / *((_QWORD *)v13 + 117);
        if ( (_DWORD)v18 != *((_DWORD *)v13 + 238) )
        {
          *((_DWORD *)v13 + 238) = v18;
          SendMessageW(a1, 0x46Au, (unsigned int)v18, 0);
        }
        return 0;
      case 0xE:
        ModuleHandleW = GetModuleHandleW(0);
        if ( LoadStringW(ModuleHandleW, 0x277u, Buffer, 256)
          && (int)StringCchPrintfW(psz, 0x400u, Buffer, *((_QWORD *)_AtlModule + 115), *((_QWORD *)_AtlModule + 117)) >= 0 )
        {
          v15 = _AtlModule;
          v16 = SysAllocString(psz);
          v17 = v16;
          v41 = v16;
          if ( !v16 )
            ATL::AtlThrowImpl(-2147024882);
          CSessionLogger::WriteToLog((int *)v15 + 182, 8, (__int64)v16);
          SysFreeString(v17);
        }
        else
        {
          CSessionLogger::WriteToLog((int *)_AtlModule + 182, 8, *((_QWORD *)_AtlModule + 115));
        }
        break;
      default:
        return 0;
    }
    PostMessageW(a1, 0x10u, 0, 0);
    return 0;
  }
  if ( v10 == 1 )
  {
    v11 = _AtlModule;
    *((_QWORD *)_AtlModule + 116) = 0;
LABEL_11:
    *((_DWORD *)v11 + 228) = 14;
  }
  return 0;
}

```

## disassembly

```asm
0x14002e450  push    rbp
0x14002e452  push    rbx
0x14002e453  push    rsi
0x14002e454  push    rdi
0x14002e455  push    r14
0x14002e457  push    r15
0x14002e459  lea     rbp, [rsp-998h]
0x14002e461  sub     rsp, 0A98h
0x14002e468  mov     rax, cs:__security_cookie
0x14002e46f  xor     rax, rsp
0x14002e472  mov     [rbp+9C0h+var_40], rax
0x14002e479  mov     ebx, edx
0x14002e47b  mov     rdi, rcx
0x14002e47e  xor     edx, edx; Val
0x14002e480  mov     r8d, 800h; Size
0x14002e486  lea     rcx, [rbp+9C0h+psz]; void *
0x14002e48d  call    memset_0
0x14002e492  xor     edx, edx; Val
0x14002e494  mov     r8d, 200h; Size
0x14002e49a  lea     rcx, [rbp+9C0h+Buffer]; void *
0x14002e49e  call    memset_0
0x14002e4a3  xor     r15d, r15d
0x14002e4a6  mov     dword ptr [rsp+0AC0h+var_A80+4], r15d
0x14002e4ab  mov     dword ptr [rsp+0AC0h+var_A88], ebx
0x14002e4af  mov     [rsp+0AC0h+var_A90], 82h
0x14002e4b7  mov     edx, 7FFFFFFFh
0x14002e4bc  lea     rcx, aBaseDiagnosisR_7; "base\\diagnosis\\ra\\ui\\filexfer.cpp"
0x14002e4c3  mov     rax, rcx
0x14002e4c6  cmp     [rax], r15w
0x14002e4ca  jz      short loc_14002E4D6
0x14002e4cc  add     rax, 2
0x14002e4d0  sub     rdx, 1
0x14002e4d4  jnz     short loc_14002E4C6
0x14002e4d6  mov     esi, 4
0x14002e4db  test    rdx, rdx
0x14002e4de  jz      short loc_14002E543
0x14002e4e0  mov     [rsp+0AC0h+UserData.Ptr], rcx
0x14002e4e5  lea     eax, [rdx+rdx]
0x14002e4e8  mov     ecx, 0FFFFFFFEh
0x14002e4ed  sub     ecx, eax
0x14002e4ef  neg     rdx
0x14002e4f2  sbb     eax, eax
0x14002e4f4  and     eax, ecx
0x14002e4f6  add     eax, 2
0x14002e4f9  mov     [rsp+0AC0h+UserData.Size], eax
0x14002e4fd  mov     dword ptr [rsp+0AC0h+UserData.0Ch], r15d
0x14002e502  lea     rax, [rsp+0AC0h+var_A90]
0x14002e507  mov     [rsp+0AC0h+var_A60], rax
0x14002e50c  mov     [rsp+0AC0h+var_A58], rsi
0x14002e511  lea     rax, [rsp+0AC0h+var_A88]
0x14002e516  mov     [rsp+0AC0h+var_A50], rax
0x14002e51b  mov     [rsp+0AC0h+var_A48], rsi
0x14002e520  lea     r9, [rsp+0AC0h+UserData]; UserData
0x14002e525  lea     r8d, [rsi-1]; UserDataCount
0x14002e529  lea     rdx, Switch_On; EventDescriptor
0x14002e530  mov     rcx, cs:?g_Logger@@3VCEventLogger@@A; RegHandle
0x14002e537  call    cs:__imp_EventWrite
0x14002e53e  nop     dword ptr [rax+rax+00h]
0x14002e543  test    ebx, ebx
0x14002e545  jz      loc_14002E82D
0x14002e54b  sub     ebx, 2
0x14002e54e  jz      loc_14002E772
0x14002e554  sub     ebx, 2
0x14002e557  jz      short loc_14002E57F
0x14002e559  cmp     ebx, 1
0x14002e55c  jnz     loc_14002E9D9
0x14002e562  mov     rax, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x14002e569  mov     [rax+3A0h], r15
0x14002e570  mov     dword ptr [rax+390h], 0Eh
0x14002e57a  jmp     loc_14002E9D9
0x14002e57f  xor     edx, edx; dwMilliseconds
0x14002e581  mov     rcx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x14002e588  mov     rcx, [rcx+350h]; hHandle
0x14002e58f  call    cs:__imp_WaitForSingleObject
0x14002e596  nop     dword ptr [rax+rax+00h]
0x14002e59b  mov     r14d, 8
0x14002e5a1  mov     r8, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x14002e5a8  test    eax, eax
0x14002e5aa  jnz     short loc_14002E5B3
0x14002e5ac  mov     [r8+390h], r14d
0x14002e5b3  mov     ecx, [r8+390h]
0x14002e5ba  sub     ecx, 7
0x14002e5bd  jz      loc_14002E728
0x14002e5c3  sub     ecx, 1
0x14002e5c6  jz      loc_14002E6FD
0x14002e5cc  sub     ecx, 5
0x14002e5cf  jz      loc_14002E6B9
0x14002e5d5  cmp     ecx, 1
0x14002e5d8  jnz     loc_14002E9D9
0x14002e5de  xor     ecx, ecx; lpModuleName
0x14002e5e0  call    cs:__imp_GetModuleHandleW
0x14002e5e7  nop     dword ptr [rax+rax+00h]
0x14002e5ec  mov     rcx, rax; hInstance
0x14002e5ef  mov     r9d, 100h; cchBufferMax
0x14002e5f5  lea     r8, [rbp+9C0h+Buffer]; lpBuffer
0x14002e5f9  mov     edx, 277h; uID
0x14002e5fe  call    cs:__imp_LoadStringW
0x14002e605  nop     dword ptr [rax+rax+00h]
0x14002e60a  test    eax, eax
0x14002e60c  jz      loc_14002E697
0x14002e612  mov     r9, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x14002e619  mov     rax, [r9+3A8h]
0x14002e620  mov     [rsp+0AC0h+var_AA0], rax
0x14002e625  mov     r9, [r9+398h]
0x14002e62c  lea     r8, [rbp+9C0h+Buffer]; unsigned __int16 *
0x14002e630  mov     edx, 400h; unsigned __int64
0x14002e635  lea     rcx, [rbp+9C0h+psz]; unsigned __int16 *
0x14002e63c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14002e641  test    eax, eax
0x14002e643  js      short loc_14002E697
0x14002e645  mov     rsi, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x14002e64c  lea     rcx, [rbp+9C0h+psz]; psz
0x14002e653  call    cs:__imp_SysAllocString
0x14002e65a  nop     dword ptr [rax+rax+00h]
0x14002e65f  mov     rbx, rax
0x14002e662  mov     [rsp+0AC0h+var_A88], rax
0x14002e667  test    rax, rax
0x14002e66a  jz      loc_14002E9FB
0x14002e670  mov     r8, rax
0x14002e673  mov     edx, r14d
0x14002e676  lea     rcx, [rsi+2D8h]
0x14002e67d  call    ?WriteToLog@CSessionLogger@@QEAAJW4_SessionEvent@@PEAG@Z; CSessionLogger::WriteToLog(_SessionEvent,ushort *)
0x14002e682  nop
0x14002e683  mov     rcx, rbx; bstrString
0x14002e686  call    cs:__imp_SysFreeString
0x14002e68d  nop     dword ptr [rax+rax+00h]
0x14002e692  jmp     loc_14002E754
0x14002e697  mov     r8, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x14002e69e  lea     rcx, [r8+2D8h]
0x14002e6a5  mov     r8, [r8+398h]
0x14002e6ac  mov     edx, r14d
0x14002e6af  call    ?WriteToLog@CSessionLogger@@QEAAJW4_SessionEvent@@PEAG@Z; CSessionLogger::WriteToLog(_SessionEvent,ushort *)
0x14002e6b4  jmp     loc_14002E754
0x14002e6b9  imul    rax, [r8+3B0h], 64h ; 'd'
0x14002e6c1  cqo
0x14002e6c3  idiv    qword ptr [r8+3A8h]
0x14002e6ca  cmp     eax, [r8+3B8h]
0x14002e6d1  jz      loc_14002E9D9
0x14002e6d7  mov     [r8+3B8h], eax
0x14002e6de  mov     r8d, eax; wParam
0x14002e6e1  xor     r9d, r9d; lParam
0x14002e6e4  mov     edx, 46Ah; Msg
0x14002e6e9  mov     rcx, rdi; hWnd
0x14002e6ec  call    cs:__imp_SendMessageW
0x14002e6f3  nop     dword ptr [rax+rax+00h]
0x14002e6f8  jmp     loc_14002E9D9
0x14002e6fd  lea     rcx, [r8+2D8h]
0x14002e704  mov     r8, [r8+398h]
0x14002e70b  mov     edx, 7
0x14002e710  call    ?WriteToLog@CSessionLogger@@QEAAJW4_SessionEvent@@PEAG@Z; CSessionLogger::WriteToLog(_SessionEvent,ushort *)
0x14002e715  mov     rax, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x14002e71c  mov     dword ptr [rax+390h], 0Eh
0x14002e726  jmp     short loc_14002E754
0x14002e728  mov     dword ptr [r8+390h], 0Dh
0x14002e733  mov     [rsp+0AC0h+var_A98], r15d; int
0x14002e738  mov     [rsp+0AC0h+var_AA0], 0FFFEh; unsigned __int16 *
0x14002e741  xor     r9d, r9d; int
0x14002e744  mov     r8, rdi; HWND
0x14002e747  mov     edx, 286h; int
0x14002e74c  lea     ecx, [rdx-77h]; int
0x14002e74f  call    ?ShowErrorMessage@@YAJHHPEAUHWND__@@JPEBGH@Z; ShowErrorMessage(int,int,HWND__ *,long,ushort const *,int)
0x14002e754  xor     r9d, r9d; lParam
0x14002e757  xor     r8d, r8d; wParam
0x14002e75a  lea     edx, [r9+10h]; Msg
0x14002e75e  mov     rcx, rdi; hWnd
0x14002e761  call    cs:__imp_PostMessageW
0x14002e768  nop     dword ptr [rax+rax+00h]
0x14002e76d  jmp     loc_14002E9D9
0x14002e772  mov     r8, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x14002e779  cmp     dword ptr [r8+390h], 0Dh
0x14002e781  jnz     loc_14002E9D9
0x14002e787  cmp     [rbp+9C0h+arg_20], 1
0x14002e78f  jnz     short loc_14002E79F
0x14002e791  mov     rcx, [r8+388h]; this
0x14002e798  call    ?Cancel@RAFileXferClient@@QEAAJXZ; RAFileXferClient::Cancel(void)
0x14002e79d  jmp     short loc_14002E81C
0x14002e79f  mov     rsi, [r8+380h]
0x14002e7a6  mov     rax, [rsi+8]
0x14002e7aa  cmp     [rax+1CCh], r15d
0x14002e7b1  jz      short loc_14002E823
0x14002e7b3  mov     rdi, [rax+1E0h]
0x14002e7ba  test    rdi, rdi
0x14002e7bd  jz      short loc_14002E823
0x14002e7bf  mov     r14, [rax+200h]
0x14002e7c6  test    r14, r14
0x14002e7c9  jz      short loc_14002E823
0x14002e7cb  mov     rbx, r15
0x14002e7ce  imul    rdx, rbx, 38h ; '8'
0x14002e7d2  add     rdx, r14; struct RECV_ENTRY *
0x14002e7d5  cmp     dword ptr [rdx], 0FFFFFC18h
0x14002e7db  jz      short loc_14002E813
0x14002e7dd  cmp     dword ptr [rdx+20h], 1
0x14002e7e1  ja      short loc_14002E813
0x14002e7e3  mov     rax, [rdi]
0x14002e7e6  jmp     short loc_14002E7FF
0x14002e7e8  mov     rcx, [rax+10h]
0x14002e7ec  cmp     rcx, [rsi]
0x14002e7ef  jz      short loc_14002E7FC
0x14002e7f1  test    rcx, rcx
0x14002e7f4  jz      short loc_14002E7FC
0x14002e7f6  cmp     dword ptr [rcx+10h], 0FFFFFF9Ch
0x14002e7fa  jz      short loc_14002E813
0x14002e7fc  mov     rax, [rax]
0x14002e7ff  cmp     rax, rdi
0x14002e802  jnz     short loc_14002E7E8
0x14002e804  mov     r8d, 1; int
0x14002e80a  mov     rcx, [rsi+8]; struct CRATicket *
0x14002e80e  call    ?AbortReceiver@@YAJPEAVCRATicket@@PEAURECV_ENTRY@@H@Z; AbortReceiver(CRATicket *,RECV_ENTRY *,int)
0x14002e813  inc     rbx
0x14002e816  cmp     rbx, 0Ah
0x14002e81a  jnz     short loc_14002E7CE
0x14002e81c  mov     r8, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x14002e823  mov     edx, 7
0x14002e828  jmp     loc_14002E9C6
0x14002e82d  mov     r8, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x14002e834  or      [r8+228h], esi
0x14002e83b  mov     [r8+3A0h], rdi
0x14002e842  mov     [r8+3B0h], r15
0x14002e849  cmp     [rbp+9C0h+arg_20], 1
0x14002e851  jnz     loc_14002E9C1
0x14002e857  mov     rcx, [r8+388h]
0x14002e85e  test    rcx, rcx
0x14002e861  jz      short loc_14002E87D
0x14002e863  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x14002e86a  nop     dword ptr [rax+rax+00h]
0x14002e86f  mov     r8, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x14002e876  mov     [r8+388h], r15
0x14002e87d  mov     dword ptr [r8+390h], 0Dh
0x14002e888  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14002e88f  mov     ecx, 50h ; 'P'; unsigned __int64
0x14002e894  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14002e899  mov     rcx, rax
0x14002e89c  mov     [rsp+0AC0h+var_A88], rax
0x14002e8a1  mov     r9, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; unsigned int
0x14002e8a8  test    rax, rax
0x14002e8ab  jz      short loc_14002E8E9
0x14002e8ad  mov     rax, [r9+340h]
0x14002e8b4  mov     [rcx+38h], rax
0x14002e8b8  mov     [rcx+40h], r15
0x14002e8bc  mov     [rcx+48h], r15
0x14002e8c0  mov     eax, 10h
0x14002e8c5  mov     rdx, rcx
0x14002e8c8  mov     [rdx], r15b
0x14002e8cb  inc     rdx
0x14002e8ce  sub     rax, 1
0x14002e8d2  jnz     short loc_14002E8C8
0x14002e8d4  lea     edx, [rax+28h]
0x14002e8d7  lea     rax, [rcx+10h]
0x14002e8db  mov     [rax], r15b
0x14002e8de  inc     rax
0x14002e8e1  sub     rdx, 1
0x14002e8e5  jnz     short loc_14002E8DB
0x14002e8e7  jmp     short loc_14002E8EC
0x14002e8e9  mov     rcx, r15
0x14002e8ec  mov     [r9+388h], rcx
0x14002e8f3  test    rcx, rcx
0x14002e8f6  jnz     short loc_14002E908
0x14002e8f8  mov     dword ptr [r9+390h], 0Eh
0x14002e903  jmp     loc_14002E9D9
0x14002e908  lea     rax, ?SendFileClientCallback@@YAXPEAURA_FILE_XFER_CLIENT_CONTEXT@@W4RAFX_STATUS@@@Z; SendFileClientCallback(RA_FILE_XFER_CLIENT_CONTEXT *,RAFX_STATUS)
0x14002e90f  mov     qword ptr [rsp+0AC0h+var_A80+8], rax
0x14002e914  mov     dword ptr [rsp+0AC0h+var_A80], 2BF20h
0x14002e91c  mov     rax, [rcx+38h]
0x14002e920  cmp     [rax+1CCh], r15d
0x14002e927  jz      short loc_14002E9A2
0x14002e929  movups  xmm0, [rsp+0AC0h+var_A80]
0x14002e92e  movdqu  xmmword ptr [rcx], xmm0
0x14002e932  mov     [rcx+28h], rcx
0x14002e936  mov     [r9+3A0h], rdi
0x14002e93d  mov     rax, [r9+340h]
0x14002e944  mov     rax, [rax+0D0h]
0x14002e94b  neg     rax
0x14002e94e  sbb     edx, edx; int
0x14002e950  mov     r8, [r9+398h]; unsigned __int16 *
0x14002e957  mov     rcx, [r9+388h]; this
0x14002e95e  call    ?SendFile@RAFileXferClient@@QEAAJJPEBGKW4__MIDL___MIDL_itf_rdpencomapi_0000_0000_0003@@@Z; RAFileXferClient::SendFile(long,ushort const *,ulong,__MIDL___MIDL_itf_rdpencomapi_0000_0000_0003)
0x14002e963  test    eax, eax
0x14002e965  jns     short loc_14002E9D9
0x14002e967  mov     rcx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x14002e96e  mov     rcx, [rcx+388h]
0x14002e975  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x14002e97c  nop     dword ptr [rax+rax+00h]
0x14002e981  mov     rax, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x14002e988  mov     [rax+388h], r15
0x14002e98f  mov     dword ptr [rax+390h], 0Eh
0x14002e999  mov     [rax+3A0h], r15
0x14002e9a0  jmp     short loc_14002E9D9
0x14002e9a2  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x14002e9a9  nop     dword ptr [rax+rax+00h]
0x14002e9ae  mov     rax, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x14002e9b5  mov     [rax+388h], r15
0x14002e9bc  jmp     loc_14002E570
0x14002e9c1  mov     edx, 5
0x14002e9c6  lea     rcx, [r8+2D8h]
0x14002e9cd  mov     r8, [r8+398h]
0x14002e9d4  call    ?WriteToLog@CSessionLogger@@QEAAJW4_SessionEvent@@PEAG@Z; CSessionLogger::WriteToLog(_SessionEvent,ushort *)
0x14002e9d9  xor     eax, eax
0x14002e9db  mov     rcx, [rbp+9C0h+var_40]
0x14002e9e2  xor     rcx, rsp; StackCookie
0x14002e9e5  call    __security_check_cookie
  ... truncated ...
```
