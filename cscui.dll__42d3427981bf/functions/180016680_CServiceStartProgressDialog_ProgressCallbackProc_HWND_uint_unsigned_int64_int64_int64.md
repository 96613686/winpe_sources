# CServiceStartProgressDialog::_ProgressCallbackProc(HWND__ *,uint,unsigned __int64,__int64,__int64)

- ea: `0x180016680`
- end: `0x180016952`
- name: `?_ProgressCallbackProc@CServiceStartProgressDialog@@CAJPEAUHWND__@@I_K_J2@Z`
- size: `722`
- prototype: `__int64 __usercall@<rax>(HWND hWnd@<rcx>, unsigned int@<edx>, unsigned __int64@<r8>, __int64@<r9>, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x180006500`
- `0x180010ff4`
- `0x180014b30`
- `0x180016680`
- `0x18001744c`

## import_xrefs

- `SHLWAPI!__imp_SHCreateThread` at `0x1800168a1`
- `SHLWAPI!__imp_SHCreateThread` at `0x1800168a1`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001670c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001670c`
- `USER32!SetForegroundWindow` at `0x180016939`
- `USER32!SetForegroundWindow` at `0x180016939`
- `USER32!SetWindowPos` at `0x180016903`
- `USER32!SetWindowPos` at `0x18001692f`
- `USER32!SetWindowPos` at `0x180016903`
- `USER32!SetWindowPos` at `0x18001692f`
- `USER32!SendMessageW` at `0x180016775`
- `USER32!SendMessageW` at `0x180016871`
- `USER32!SendMessageW` at `0x180016886`
- `USER32!SendMessageW` at `0x180016775`
- `USER32!SendMessageW` at `0x180016871`
- `USER32!SendMessageW` at `0x180016886`

## pseudocode

```c
__int64 __fastcall CServiceStartProgressDialog::_ProgressCallbackProc(
        HWND hWnd,
        int a2,
        __int64 a3,
        __int64 a4,
        void *pData)
{
  int v5; // ebp
  int v8; // edx
  int v9; // edx
  UstCommon::CImpersonator *v10; // rcx
  unsigned int v11; // edi

  v5 = 0;
  if ( a2 )
  {
    v8 = a2 - 2;
    if ( v8 )
    {
      v9 = v8 - 2;
      if ( v9 )
      {
        if ( v9 == 1 )
        {
          if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_c013a7ee7daf377cb39f4e99660eb156_Traceguids);
          }
          *((_QWORD *)pData + 3) = 0;
        }
      }
      else
      {
        if ( (unsigned int)SHHasTimeoutElapsed(*((_DWORD *)pData + 9), 0x3E8u) )
          *((_DWORD *)pData + 9) = GetTickCount64();
        if ( *((_DWORD *)pData + 8) && (unsigned int)SHHasTimeoutElapsed(*((_DWORD *)pData + 10), 0xBB8u) )
        {
          if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_c013a7ee7daf377cb39f4e99660eb156_Traceguids);
          }
          SendMessageW(*((HWND *)pData + 3), 0x466u, 8u, 0);
        }
      }
    }
    else
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0 )
      {
        WPP_SF_dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          14,
          WPP_c013a7ee7daf377cb39f4e99660eb156_Traceguids,
          (unsigned int)a3,
          a3);
        v10 = WPP_GLOBAL_Control;
      }
      if ( a3 == 8 || a3 == 2 )
      {
        if ( v10 != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control && (*((_DWORD *)v10 + 7) & 0x40000) != 0 )
          WPP_SF_(*((_QWORD *)v10 + 2), 15, WPP_c013a7ee7daf377cb39f4e99660eb156_Traceguids);
      }
      else
      {
        if ( v10 != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control && (*((_DWORD *)v10 + 7) & 0x40000) != 0 )
          WPP_SF_(*((_QWORD *)v10 + 2), 16, WPP_c013a7ee7daf377cb39f4e99660eb156_Traceguids);
        return 1;
      }
    }
    return (unsigned int)v5;
  }
  if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_c013a7ee7daf377cb39f4e99660eb156_Traceguids);
  }
  v11 = 1;
  *((_QWORD *)pData + 3) = hWnd;
  SendMessageW(hWnd, 0x467u, 1u, 0);
  SendMessageW(hWnd, 0x46Bu, 1u, 100);
  _InterlockedAdd((volatile signed __int32 *)pData + 2, 1u);
  if ( !SHCreateThread(CServiceStartProgressDialog::_WorkerThreadProc, pData, 0x18u, 0) )
  {
    v5 = -2147467259;
    CRefCounted::ReleaseReference((CRefCounted *)pData);
    if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_c013a7ee7daf377cb39f4e99660eb156_Traceguids);
    }
  }
  SetWindowPos(*((HWND *)pData + 3), HWND_MESSAGE|0x2LL, 0, 0, 0, 0, 0x83u);
  SetWindowPos(*((HWND *)pData + 3), (HWND)0xFFFFFFFFFFFFFFFELL, 0, 0, 0, 0, 0x43u);
  SetForegroundWindow(*((HWND *)pData + 3));
  if ( v5 >= 0 )
    return (unsigned int)v5;
  return v11;
}

```

## disassembly

```asm
0x180016680  push    rbx
0x180016682  push    rbp
0x180016683  push    rsi
0x180016684  push    rdi
0x180016685  push    r14
0x180016687  sub     rsp, 40h
0x18001668b  xor     ebp, ebp
0x18001668d  mov     rsi, r8
0x180016690  mov     r14, rcx
0x180016693  test    edx, edx
0x180016695  jz      loc_180016821
0x18001669b  sub     edx, 2
0x18001669e  jz      loc_180016780
0x1800166a4  sub     edx, 2
0x1800166a7  jz      short loc_1800166F3
0x1800166a9  cmp     edx, 1
0x1800166ac  jnz     loc_180016943
0x1800166b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800166b9  lea     rbx, WPP_GLOBAL_Control
0x1800166c0  cmp     rcx, rbx
0x1800166c3  jz      short loc_1800166E2
0x1800166c5  mov     edi, 40000h
0x1800166ca  test    [rcx+1Ch], edi
0x1800166cd  jz      short loc_1800166E2
0x1800166cf  mov     rcx, [rcx+10h]
0x1800166d3  lea     edx, [rbp+0Dh]
0x1800166d6  lea     r8, WPP_c013a7ee7daf377cb39f4e99660eb156_Traceguids
0x1800166dd  call    WPP_SF_
0x1800166e2  mov     rax, [rsp+68h+pData]
0x1800166ea  mov     [rax+18h], rbp
0x1800166ee  jmp     loc_180016943
0x1800166f3  mov     rsi, [rsp+68h+pData]
0x1800166fb  mov     edx, 3E8h; unsigned int
0x180016700  mov     ecx, [rsi+24h]; unsigned int
0x180016703  call    ?SHHasTimeoutElapsed@@YAHKK@Z; SHHasTimeoutElapsed(ulong,ulong)
0x180016708  test    eax, eax
0x18001670a  jz      short loc_180016715
0x18001670c  call    cs:__imp_GetTickCount64
0x180016712  mov     [rsi+24h], eax
0x180016715  cmp     [rsi+20h], ebp
0x180016718  jz      loc_180016943
0x18001671e  mov     ecx, [rsi+28h]; unsigned int
0x180016721  mov     edx, 0BB8h; unsigned int
0x180016726  call    ?SHHasTimeoutElapsed@@YAHKK@Z; SHHasTimeoutElapsed(ulong,ulong)
0x18001672b  test    eax, eax
0x18001672d  jz      loc_180016943
0x180016733  mov     rcx, cs:WPP_GLOBAL_Control
0x18001673a  lea     rbx, WPP_GLOBAL_Control
0x180016741  cmp     rcx, rbx
0x180016744  jz      short loc_180016765
0x180016746  mov     edi, 40000h
0x18001674b  test    [rcx+1Ch], edi
0x18001674e  jz      short loc_180016765
0x180016750  mov     rcx, [rcx+10h]
0x180016754  lea     r8, WPP_c013a7ee7daf377cb39f4e99660eb156_Traceguids
0x18001675b  mov     edx, 11h
0x180016760  call    WPP_SF_
0x180016765  mov     rcx, [rsi+18h]; hWnd
0x180016769  xor     r9d, r9d; lParam
0x18001676c  mov     edx, 466h; Msg
0x180016771  lea     r8d, [r9+8]; wParam
0x180016775  call    cs:__imp_SendMessageW
0x18001677b  jmp     loc_180016943
0x180016780  mov     rcx, cs:WPP_GLOBAL_Control
0x180016787  lea     rbx, WPP_GLOBAL_Control
0x18001678e  mov     edi, 40000h
0x180016793  cmp     rcx, rbx
0x180016796  jz      short loc_1800167C0
0x180016798  test    [rcx+1Ch], edi
0x18001679b  jz      short loc_1800167C0
0x18001679d  mov     rcx, [rcx+10h]
0x1800167a1  lea     r8, WPP_c013a7ee7daf377cb39f4e99660eb156_Traceguids
0x1800167a8  mov     edx, 0Eh
0x1800167ad  mov     [rsp+68h+var_48], esi
0x1800167b1  mov     r9d, esi
0x1800167b4  call    WPP_SF_dd
0x1800167b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800167c0  cmp     rsi, 8
0x1800167c4  jz      short loc_1800167F5
0x1800167c6  cmp     rsi, 2
0x1800167ca  jz      short loc_1800167F5
0x1800167cc  cmp     rcx, rbx
0x1800167cf  jz      short loc_1800167EB
0x1800167d1  test    [rcx+1Ch], edi
0x1800167d4  jz      short loc_1800167EB
0x1800167d6  mov     rcx, [rcx+10h]
0x1800167da  lea     r8, WPP_c013a7ee7daf377cb39f4e99660eb156_Traceguids
0x1800167e1  mov     edx, 10h
0x1800167e6  call    WPP_SF_
0x1800167eb  mov     ebp, 1
0x1800167f0  jmp     loc_180016943
0x1800167f5  cmp     rcx, rbx
0x1800167f8  jz      loc_180016943
0x1800167fe  test    [rcx+1Ch], edi
0x180016801  jz      loc_180016943
0x180016807  mov     rcx, [rcx+10h]
0x18001680b  lea     r8, WPP_c013a7ee7daf377cb39f4e99660eb156_Traceguids
0x180016812  mov     edx, 0Fh
0x180016817  call    WPP_SF_
0x18001681c  jmp     loc_180016943
0x180016821  mov     rcx, cs:WPP_GLOBAL_Control
0x180016828  lea     rbx, WPP_GLOBAL_Control
0x18001682f  cmp     rcx, rbx
0x180016832  jz      short loc_180016853
0x180016834  mov     edi, 40000h
0x180016839  test    [rcx+1Ch], edi
0x18001683c  jz      short loc_180016853
0x18001683e  mov     rcx, [rcx+10h]
0x180016842  lea     r8, WPP_c013a7ee7daf377cb39f4e99660eb156_Traceguids
0x180016849  mov     edx, 0Bh
0x18001684e  call    WPP_SF_
0x180016853  mov     rsi, [rsp+68h+pData]
0x18001685b  xor     r9d, r9d; lParam
0x18001685e  mov     edx, 467h; Msg
0x180016863  mov     rcx, r14; hWnd
0x180016866  lea     edi, [r9+1]
0x18001686a  mov     [rsi+18h], r14
0x18001686e  mov     r8d, edi; wParam
0x180016871  call    cs:__imp_SendMessageW
0x180016877  lea     r9d, [rdi+63h]; lParam
0x18001687b  mov     r8d, edi; wParam
0x18001687e  mov     edx, 46Bh; Msg
0x180016883  mov     rcx, r14; hWnd
0x180016886  call    cs:__imp_SendMessageW
0x18001688c  lock add [rsi+8], edi
0x180016890  xor     r9d, r9d; pfnCallback
0x180016893  lea     r8d, [rdi+17h]; flags
0x180016897  mov     rdx, rsi; pData
0x18001689a  lea     rcx, ?_WorkerThreadProc@CServiceStartProgressDialog@@CAKPEAX@Z; pfnThreadProc
0x1800168a1  call    cs:__imp_SHCreateThread
0x1800168a7  test    eax, eax
0x1800168a9  jnz     short loc_1800168DD
0x1800168ab  mov     rcx, rsi; this
0x1800168ae  mov     ebp, 80004005h
0x1800168b3  call    ?ReleaseReference@CRefCounted@@QEAAXXZ; CRefCounted::ReleaseReference(void)
0x1800168b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800168bf  cmp     rcx, rbx
0x1800168c2  jz      short loc_1800168DD
0x1800168c4  test    byte ptr [rcx+1Ch], 2
0x1800168c8  jz      short loc_1800168DD
0x1800168ca  mov     rcx, [rcx+10h]
0x1800168ce  lea     edx, [rdi+0Bh]
0x1800168d1  lea     r8, WPP_c013a7ee7daf377cb39f4e99660eb156_Traceguids
0x1800168d8  call    WPP_SF_
0x1800168dd  mov     rcx, [rsi+18h]; hWnd
0x1800168e1  xor     r9d, r9d; Y
0x1800168e4  mov     [rsp+68h+uFlags], 83h; uFlags
0x1800168ec  xor     r8d, r8d; X
0x1800168ef  mov     [rsp+68h+cy], 0; cy
0x1800168f7  or      rdx, 0FFFFFFFFFFFFFFFFh; hWndInsertAfter
0x1800168fb  mov     [rsp+68h+var_48], 0; cx
0x180016903  call    cs:__imp_SetWindowPos
0x180016909  mov     rcx, [rsi+18h]; hWnd
0x18001690d  xor     r9d, r9d; Y
0x180016910  mov     [rsp+68h+uFlags], 43h ; 'C'; uFlags
0x180016918  xor     r8d, r8d; X
0x18001691b  mov     [rsp+68h+cy], 0; cy
0x180016923  mov     [rsp+68h+var_48], 0; cx
0x18001692b  lea     rdx, [r9-2]; hWndInsertAfter
0x18001692f  call    cs:__imp_SetWindowPos
0x180016935  mov     rcx, [rsi+18h]; hWnd
0x180016939  call    cs:__imp_SetForegroundWindow
0x18001693f  test    ebp, ebp
0x180016941  js      short loc_180016945
0x180016943  mov     edi, ebp
0x180016945  mov     eax, edi
0x180016947  add     rsp, 40h
0x18001694b  pop     r14
0x18001694d  pop     rdi
0x18001694e  pop     rsi
0x18001694f  pop     rbp
0x180016950  pop     rbx
0x180016951  retn
```
