# CClipServer::ClipThreadMain(void)

- ea: `0x14003a8c0`
- end: `0x14003adb9`
- name: `?ClipThreadMain@CClipServer@@EEAAXXZ`
- size: `1273`
- prototype: `void __fastcall(CClipServer *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `installer_update`

## callers

- `0x14003ead0`

## callees

- `0x140004b1c`
- `0x1400056c4`
- `0x140005750`
- `0x1400081ac`
- `0x1400081d0`
- `0x14003a470`
- `0x14003a8c0`
- `0x14003bdd0`
- `0x14003ed60`
- `0x14004624c`
- `0x140046340`
- `0x14006b010`

## import_xrefs

- `ole32!OleUninitialize` at `0x14003ada6`
- `ole32!OleUninitialize` at `0x14003ada6`
- `ole32!OleInitialize` at `0x14003a8d2`
- `ole32!OleInitialize` at `0x14003a8d2`

## string_xrefs

- `0x14003a9fc`: `CreateRdrWindow failed!`
- `0x14003aa59`: `RegisterForUpdateNotifications failed!`
- `0x14003aac7`: `Failed to create receive thread!`
- `0x14003ab1f`: `Failed to start the receive thread!`
- `0x14003ab8d`: `Failed to create the data request thread!`
- `0x14003abe5`: `Failed to start the data request thread!`
- `0x14003ad12`: `Error while ending receive thread!`

## pseudocode

```c
void __fastcall CClipServer::ClipThreadMain(CClipServer *this)
{
  HRESULT v2; // r15d
  unsigned __int16 *v3; // rcx
  int RdrWindow; // edi
  __int64 (*v5)(HWND, unsigned int, unsigned __int64, __int64); // r8
  unsigned int v6; // eax
  int v7; // edx
  const char *v8; // rcx
  unsigned __int16 *v9; // rdx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  unsigned int v11; // eax
  _QWORD *v12; // rdi
  __int64 v13; // rcx
  int v14; // ebp
  unsigned int v15; // eax
  _QWORD *v16; // rbx
  __int64 v17; // rcx
  const unsigned __int16 *v18; // [rsp+20h] [rbp-48h]
  __int64 v19; // [rsp+28h] [rbp-40h]
  int v20; // [rsp+28h] [rbp-40h]

  v2 = OleInitialize(0);
  RdrWindow = CClipServer::Initialize((CClipServer *)((char *)this + 8));
  if ( RdrWindow >= 0 )
  {
    RdrWindow = CRdrWnd::RegisterRdrWindowClass(v3, *((HINSTANCE *)this + 28), v5, (unsigned __int16 *)this + 108);
    if ( RdrWindow >= 0 )
    {
      RdrWindow = CRdrWnd::CreateRdrWindow((HWND *)this + 29, v9, *((HINSTANCE *)this + 28), this, v18);
      if ( RdrWindow >= 0 )
      {
        RdrWindow = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 44) + 24LL))(
                      *((_QWORD *)this + 44),
                      *((_QWORD *)this + 29));
        if ( RdrWindow >= 0 )
        {
          RdrWindow = (*(__int64 (__fastcall **)(_QWORD, void (__fastcall *)(CClipServer *), CClipServer *, char *))(**((_QWORD **)this + 84) + 56LL))(
                        *((_QWORD *)this + 84),
                        CClipServer::StaticRcvThreadMain,
                        this,
                        (char *)this + 648);
          if ( RdrWindow >= 0 )
          {
            RdrWindow = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 81) + 32LL))(
                          *((_QWORD *)this + 81),
                          0);
            if ( RdrWindow >= 0 )
            {
              RdrWindow = (*(__int64 (__fastcall **)(_QWORD, void (__fastcall *)(CClipServer *), CClipServer *, char *))(**((_QWORD **)this + 84) + 56LL))(
                            *((_QWORD *)this + 84),
                            CClipServer::StaticDataRequestThreadMain,
                            this,
                            (char *)this + 664);
              if ( RdrWindow >= 0 )
              {
                RdrWindow = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 83) + 32LL))(
                              *((_QWORD *)this + 83),
                              0);
                if ( RdrWindow >= 0 )
                {
                  RdrWindow = CClipServer::BindNotificationSinks(this);
                  if ( RdrWindow >= 0 )
                  {
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
                    {
                      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                      WPP_SF_d(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        37,
                        WPP_bda84ad720bd303d3567a2435a9ed67b_Traceguids,
                        CurrentThreadActivityIdPrefix);
                    }
                    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 82) + 64LL))(*((_QWORD *)this + 82));
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
                    {
                      v11 = RdpWppGetCurrentThreadActivityIdPrefix();
                      WPP_SF_d(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        38,
                        WPP_bda84ad720bd303d3567a2435a9ed67b_Traceguids,
                        v11);
                    }
                  }
                  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    v6 = RdpWppGetCurrentThreadActivityIdPrefix();
                    v7 = 36;
                    v8 = "BindNotificationSinks failed!";
                    goto LABEL_6;
                  }
                }
                else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                       && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                       && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  v6 = RdpWppGetCurrentThreadActivityIdPrefix();
                  v7 = 35;
                  v8 = "Failed to start the data request thread!";
                  goto LABEL_6;
                }
              }
              else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                     && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                     && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v6 = RdpWppGetCurrentThreadActivityIdPrefix();
                v7 = 34;
                v8 = "Failed to create the data request thread!";
                goto LABEL_6;
              }
            }
            else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                   && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                   && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v6 = RdpWppGetCurrentThreadActivityIdPrefix();
              v7 = 33;
              v8 = "Failed to start the receive thread!";
              goto LABEL_6;
            }
          }
          else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v6 = RdpWppGetCurrentThreadActivityIdPrefix();
            v7 = 32;
            v8 = "Failed to create receive thread!";
            goto LABEL_6;
          }
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
               && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v6 = RdpWppGetCurrentThreadActivityIdPrefix();
          v7 = 31;
          v8 = "RegisterForUpdateNotifications failed!";
          goto LABEL_6;
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v6 = RdpWppGetCurrentThreadActivityIdPrefix();
        v7 = 30;
        v8 = "CreateRdrWindow failed!";
        goto LABEL_6;
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v6 = RdpWppGetCurrentThreadActivityIdPrefix();
      v7 = 29;
      v8 = "RegisterRdrWindowClass failed!";
      goto LABEL_6;
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v6 = RdpWppGetCurrentThreadActivityIdPrefix();
    v7 = 28;
    v8 = "Failed to initialize CClipServer!";
LABEL_6:
    v20 = RdrWindow;
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v7,
      (unsigned int)WPP_bda84ad720bd303d3567a2435a9ed67b_Traceguids,
      v6,
      (__int64)v8,
      v20);
  }
  v12 = (_QWORD *)((char *)this + 648);
  v13 = *((_QWORD *)this + 81);
  if ( v13 )
  {
    v14 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v13 + 56LL))(v13, 0);
    if ( v14 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v15 = RdpWppGetCurrentThreadActivityIdPrefix();
      LODWORD(v19) = v14;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        39,
        (unsigned int)WPP_bda84ad720bd303d3567a2435a9ed67b_Traceguids,
        v15,
        (__int64)"Error while ending receive thread!",
        v19);
    }
    if ( *v12 )
    {
      TCntPtr<IRdpHintApiEventSink>::SafeRelease((char *)this + 648);
      *v12 = 0;
      TCntPtr<IRdrVirtualChannel>::SafeAddRef((char *)this + 648);
    }
  }
  v16 = (_QWORD *)((char *)this + 664);
  v17 = *((_QWORD *)this + 83);
  if ( v17 )
  {
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v17 + 56LL))(v17, 0);
    if ( *v16 )
    {
      TCntPtr<IRdpHintApiEventSink>::SafeRelease((char *)this + 664);
      *v16 = 0;
      TCntPtr<IRdrVirtualChannel>::SafeAddRef((char *)this + 664);
    }
  }
  CClipServer::Terminate((CClipServer *)((char *)this + 8));
  if ( v2 >= 0 )
    OleUninitialize();
}

```

## disassembly

```asm
0x14003a8c0  push    rbx
0x14003a8c2  push    rbp
0x14003a8c3  push    rsi
0x14003a8c4  push    rdi
0x14003a8c5  push    r14
0x14003a8c7  push    r15
0x14003a8c9  sub     rsp, 38h
0x14003a8cd  mov     rsi, rcx
0x14003a8d0  xor     ecx, ecx; pvReserved
0x14003a8d2  call    cs:__imp_OleInitialize
0x14003a8d8  lea     rcx, [rsi+8]; this
0x14003a8dc  mov     r15d, eax
0x14003a8df  call    ?Initialize@CClipServer@@MEAAJXZ; CClipServer::Initialize(void)
0x14003a8e4  mov     edi, eax
0x14003a8e6  mov     bpl, 8
0x14003a8e9  test    eax, eax
0x14003a8eb  jns     short loc_14003A951
0x14003a8ed  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a8f4  lea     rbx, WPP_GLOBAL_Control
0x14003a8fb  cmp     rcx, rbx
0x14003a8fe  jz      loc_14003ACD2
0x14003a904  test    [rcx+1Ch], bpl
0x14003a908  jz      loc_14003ACD2
0x14003a90e  cmp     byte ptr [rcx+19h], 2
0x14003a912  jb      loc_14003ACD2
0x14003a918  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14003a91d  mov     edx, 1Ch
0x14003a922  lea     rcx, aFailedToInitia_17; "Failed to initialize CClipServer!"
0x14003a929  mov     dword ptr [rsp+68h+var_40], edi
0x14003a92d  lea     r8, WPP_bda84ad720bd303d3567a2435a9ed67b_Traceguids
0x14003a934  mov     [rsp+68h+var_48], rcx
0x14003a939  mov     r9d, eax
0x14003a93c  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a943  mov     rcx, [rcx+10h]
0x14003a947  call    WPP_SF_DsD
0x14003a94c  jmp     loc_14003ACD2
0x14003a951  mov     rdx, [rsi+0E0h]; HINSTANCE
0x14003a958  lea     r9, [rsi+0D8h]; unsigned __int16 *
0x14003a95f  call    ?RegisterRdrWindowClass@CRdrWnd@@SAJPEAGPEAUHINSTANCE__@@P6A_JPEAUHWND__@@I_K_J@Z0@Z; CRdrWnd::RegisterRdrWindowClass(ushort *,HINSTANCE__ *,__int64 (*)(HWND__ *,uint,unsigned __int64,__int64),ushort *)
0x14003a964  mov     edi, eax
0x14003a966  test    eax, eax
0x14003a968  jns     short loc_14003A9A8
0x14003a96a  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a971  lea     rbx, WPP_GLOBAL_Control
0x14003a978  cmp     rcx, rbx
0x14003a97b  jz      loc_14003ACD2
0x14003a981  test    [rcx+1Ch], bpl
0x14003a985  jz      loc_14003ACD2
0x14003a98b  cmp     byte ptr [rcx+19h], 2
0x14003a98f  jb      loc_14003ACD2
0x14003a995  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14003a99a  mov     edx, 1Dh
0x14003a99f  lea     rcx, aRegisterrdrwin; "RegisterRdrWindowClass failed!"
0x14003a9a6  jmp     short loc_14003A929
0x14003a9a8  mov     r8, [rsi+0E0h]; HINSTANCE
0x14003a9af  lea     rbx, [rsi+0E8h]
0x14003a9b6  mov     rcx, rbx; HWND *
0x14003a9b9  mov     r9, rsi; void *
0x14003a9bc  call    ?CreateRdrWindow@CRdrWnd@@SAJPEAPEAUHWND__@@PEAGPEAUHINSTANCE__@@PEAXPEBG@Z; CRdrWnd::CreateRdrWindow(HWND__ * *,ushort *,HINSTANCE__ *,void *,ushort const *)
0x14003a9c1  mov     edi, eax
0x14003a9c3  test    eax, eax
0x14003a9c5  jns     short loc_14003AA08
0x14003a9c7  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a9ce  lea     rbx, WPP_GLOBAL_Control
0x14003a9d5  cmp     rcx, rbx
0x14003a9d8  jz      loc_14003ACD2
0x14003a9de  test    [rcx+1Ch], bpl
0x14003a9e2  jz      loc_14003ACD2
0x14003a9e8  cmp     byte ptr [rcx+19h], 2
0x14003a9ec  jb      loc_14003ACD2
0x14003a9f2  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14003a9f7  mov     edx, 1Eh
0x14003a9fc  lea     rcx, aCreaterdrwindo; "CreateRdrWindow failed!"
0x14003aa03  jmp     loc_14003A929
0x14003aa08  mov     rcx, [rsi+160h]
0x14003aa0f  mov     rdx, [rbx]
0x14003aa12  mov     rax, [rcx]
0x14003aa15  mov     rax, [rax+18h]
0x14003aa19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003aa1e  mov     edi, eax
0x14003aa20  test    eax, eax
0x14003aa22  jns     short loc_14003AA65
0x14003aa24  mov     rcx, cs:WPP_GLOBAL_Control
0x14003aa2b  lea     rbx, WPP_GLOBAL_Control
0x14003aa32  cmp     rcx, rbx
0x14003aa35  jz      loc_14003ACD2
0x14003aa3b  test    [rcx+1Ch], bpl
0x14003aa3f  jz      loc_14003ACD2
0x14003aa45  cmp     byte ptr [rcx+19h], 2
0x14003aa49  jb      loc_14003ACD2
0x14003aa4f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14003aa54  mov     edx, 1Fh
0x14003aa59  lea     rcx, aRegisterforupd; "RegisterForUpdateNotifications failed!"
0x14003aa60  jmp     loc_14003A929
0x14003aa65  mov     rcx, [rsi+2A0h]
0x14003aa6c  lea     rbx, [rsi+288h]
0x14003aa73  mov     r9, rbx
0x14003aa76  lea     rdx, ?StaticRcvThreadMain@CClipServer@@CAXPEAX@Z; CClipServer::StaticRcvThreadMain(void *)
0x14003aa7d  mov     r8, rsi
0x14003aa80  mov     rax, [rcx]
0x14003aa83  mov     rax, [rax+38h]
0x14003aa87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003aa8c  mov     edi, eax
0x14003aa8e  test    eax, eax
0x14003aa90  jns     short loc_14003AAD3
0x14003aa92  mov     rcx, cs:WPP_GLOBAL_Control
0x14003aa99  lea     rbx, WPP_GLOBAL_Control
0x14003aaa0  cmp     rcx, rbx
0x14003aaa3  jz      loc_14003ACD2
0x14003aaa9  test    [rcx+1Ch], bpl
0x14003aaad  jz      loc_14003ACD2
0x14003aab3  cmp     byte ptr [rcx+19h], 2
0x14003aab7  jb      loc_14003ACD2
0x14003aabd  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14003aac2  mov     edx, 20h ; ' '
0x14003aac7  lea     rcx, aFailedToCreate_11; "Failed to create receive thread!"
0x14003aace  jmp     loc_14003A929
0x14003aad3  mov     rcx, [rbx]
0x14003aad6  xor     edx, edx
0x14003aad8  mov     rax, [rcx]
0x14003aadb  mov     rax, [rax+20h]
0x14003aadf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003aae4  mov     edi, eax
0x14003aae6  test    eax, eax
0x14003aae8  jns     short loc_14003AB2B
0x14003aaea  mov     rcx, cs:WPP_GLOBAL_Control
0x14003aaf1  lea     rbx, WPP_GLOBAL_Control
0x14003aaf8  cmp     rcx, rbx
0x14003aafb  jz      loc_14003ACD2
0x14003ab01  test    [rcx+1Ch], bpl
0x14003ab05  jz      loc_14003ACD2
0x14003ab0b  cmp     byte ptr [rcx+19h], 2
0x14003ab0f  jb      loc_14003ACD2
0x14003ab15  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14003ab1a  mov     edx, 21h ; '!'
0x14003ab1f  lea     rcx, aFailedToStartT; "Failed to start the receive thread!"
0x14003ab26  jmp     loc_14003A929
0x14003ab2b  mov     rcx, [rsi+2A0h]
0x14003ab32  lea     rbx, [rsi+298h]
0x14003ab39  mov     r9, rbx
0x14003ab3c  lea     rdx, ?StaticDataRequestThreadMain@CClipServer@@CAXPEAX@Z; CClipServer::StaticDataRequestThreadMain(void *)
0x14003ab43  mov     r8, rsi
0x14003ab46  mov     rax, [rcx]
0x14003ab49  mov     rax, [rax+38h]
0x14003ab4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003ab52  mov     edi, eax
0x14003ab54  test    eax, eax
0x14003ab56  jns     short loc_14003AB99
0x14003ab58  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ab5f  lea     rbx, WPP_GLOBAL_Control
0x14003ab66  cmp     rcx, rbx
0x14003ab69  jz      loc_14003ACD2
0x14003ab6f  test    [rcx+1Ch], bpl
0x14003ab73  jz      loc_14003ACD2
0x14003ab79  cmp     byte ptr [rcx+19h], 2
0x14003ab7d  jb      loc_14003ACD2
0x14003ab83  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14003ab88  mov     edx, 22h ; '"'
0x14003ab8d  lea     rcx, aFailedToCreate_22; "Failed to create the data request threa"...
0x14003ab94  jmp     loc_14003A929
0x14003ab99  mov     rcx, [rbx]
0x14003ab9c  xor     edx, edx
0x14003ab9e  mov     rax, [rcx]
0x14003aba1  mov     rax, [rax+20h]
0x14003aba5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003abaa  mov     edi, eax
0x14003abac  test    eax, eax
0x14003abae  jns     short loc_14003ABF1
0x14003abb0  mov     rcx, cs:WPP_GLOBAL_Control
0x14003abb7  lea     rbx, WPP_GLOBAL_Control
0x14003abbe  cmp     rcx, rbx
0x14003abc1  jz      loc_14003ACD2
0x14003abc7  test    [rcx+1Ch], bpl
0x14003abcb  jz      loc_14003ACD2
0x14003abd1  cmp     byte ptr [rcx+19h], 2
0x14003abd5  jb      loc_14003ACD2
0x14003abdb  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14003abe0  mov     edx, 23h ; '#'
0x14003abe5  lea     rcx, aFailedToStartT_1; "Failed to start the data request thread"...
0x14003abec  jmp     loc_14003A929
0x14003abf1  mov     rcx, rsi; this
0x14003abf4  call    ?BindNotificationSinks@CClipServer@@EEAAJXZ; CClipServer::BindNotificationSinks(void)
0x14003abf9  mov     edi, eax
0x14003abfb  test    eax, eax
0x14003abfd  jns     short loc_14003AC40
0x14003abff  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ac06  lea     rbx, WPP_GLOBAL_Control
0x14003ac0d  cmp     rcx, rbx
0x14003ac10  jz      loc_14003ACD2
0x14003ac16  test    [rcx+1Ch], bpl
0x14003ac1a  jz      loc_14003ACD2
0x14003ac20  cmp     byte ptr [rcx+19h], 2
0x14003ac24  jb      loc_14003ACD2
0x14003ac2a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14003ac2f  mov     edx, 24h ; '$'
0x14003ac34  lea     rcx, aBindnotificati; "BindNotificationSinks failed!"
0x14003ac3b  jmp     loc_14003A929
0x14003ac40  mov     rax, cs:WPP_GLOBAL_Control
0x14003ac47  lea     rbx, WPP_GLOBAL_Control
0x14003ac4e  cmp     rax, rbx
0x14003ac51  jz      short loc_14003AC83
0x14003ac53  test    byte ptr [rax+1Ch], 1
0x14003ac57  jz      short loc_14003AC83
0x14003ac59  cmp     byte ptr [rax+19h], 5
0x14003ac5d  jb      short loc_14003AC83
0x14003ac5f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14003ac64  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ac6b  lea     r8, WPP_bda84ad720bd303d3567a2435a9ed67b_Traceguids
0x14003ac72  mov     edx, 25h ; '%'
0x14003ac77  mov     r9d, eax
0x14003ac7a  mov     rcx, [rcx+10h]
0x14003ac7e  call    WPP_SF_d
0x14003ac83  mov     rcx, [rsi+290h]
0x14003ac8a  mov     rax, [rcx]
0x14003ac8d  mov     rax, [rax+40h]
0x14003ac91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003ac96  mov     rax, cs:WPP_GLOBAL_Control
0x14003ac9d  cmp     rax, rbx
0x14003aca0  jz      short loc_14003ACD2
0x14003aca2  test    byte ptr [rax+1Ch], 1
0x14003aca6  jz      short loc_14003ACD2
0x14003aca8  cmp     byte ptr [rax+19h], 5
0x14003acac  jb      short loc_14003ACD2
0x14003acae  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14003acb3  mov     rcx, cs:WPP_GLOBAL_Control
0x14003acba  lea     r8, WPP_bda84ad720bd303d3567a2435a9ed67b_Traceguids
0x14003acc1  mov     edx, 26h ; '&'
0x14003acc6  mov     r9d, eax
0x14003acc9  mov     rcx, [rcx+10h]
0x14003accd  call    WPP_SF_d
0x14003acd2  lea     rdi, [rsi+288h]
0x14003acd9  mov     rcx, [rdi]
0x14003acdc  test    rcx, rcx
0x14003acdf  jz      short loc_14003AD5E
0x14003ace1  mov     rax, [rcx]
0x14003ace4  xor     edx, edx
0x14003ace6  mov     rax, [rax+38h]
0x14003acea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003acef  mov     ebp, eax
0x14003acf1  test    eax, eax
0x14003acf3  jns     short loc_14003AD41
0x14003acf5  mov     rcx, cs:WPP_GLOBAL_Control
0x14003acfc  cmp     rcx, rbx
0x14003acff  jz      short loc_14003AD41
0x14003ad01  test    byte ptr [rcx+1Ch], 8
0x14003ad05  jz      short loc_14003AD41
0x14003ad07  cmp     byte ptr [rcx+19h], 2
0x14003ad0b  jb      short loc_14003AD41
0x14003ad0d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14003ad12  lea     rcx, aErrorWhileEndi; "Error while ending receive thread!"
0x14003ad19  mov     dword ptr [rsp+68h+var_40], ebp
0x14003ad1d  mov     [rsp+68h+var_48], rcx
0x14003ad22  lea     r8, WPP_bda84ad720bd303d3567a2435a9ed67b_Traceguids
0x14003ad29  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ad30  mov     edx, 27h ; '''
0x14003ad35  mov     r9d, eax
0x14003ad38  mov     rcx, [rcx+10h]
0x14003ad3c  call    WPP_SF_DsD
0x14003ad41  cmp     qword ptr [rdi], 0
0x14003ad45  jz      short loc_14003AD5E
0x14003ad47  mov     rcx, rdi
0x14003ad4a  call    ?SafeRelease@?$TCntPtr@VIRdpHintApiEventSink@@@@AEAAXXZ; TCntPtr<IRdpHintApiEventSink>::SafeRelease(void)
0x14003ad4f  mov     rcx, rdi
0x14003ad52  mov     qword ptr [rdi], 0
0x14003ad59  call    ?SafeAddRef@?$TCntPtr@VIRdrVirtualChannel@@@@AEAAXXZ; TCntPtr<IRdrVirtualChannel>::SafeAddRef(void)
0x14003ad5e  lea     rbx, [rsi+298h]
0x14003ad65  mov     rcx, [rbx]
0x14003ad68  test    rcx, rcx
0x14003ad6b  jz      short loc_14003AD98
0x14003ad6d  mov     rax, [rcx]
0x14003ad70  xor     edx, edx
0x14003ad72  mov     rax, [rax+38h]
0x14003ad76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003ad7b  cmp     qword ptr [rbx], 0
0x14003ad7f  jz      short loc_14003AD98
0x14003ad81  mov     rcx, rbx
0x14003ad84  call    ?SafeRelease@?$TCntPtr@VIRdpHintApiEventSink@@@@AEAAXXZ; TCntPtr<IRdpHintApiEventSink>::SafeRelease(void)
0x14003ad89  mov     rcx, rbx
0x14003ad8c  mov     qword ptr [rbx], 0
0x14003ad93  call    ?SafeAddRef@?$TCntPtr@VIRdrVirtualChannel@@@@AEAAXXZ; TCntPtr<IRdrVirtualChannel>::SafeAddRef(void)
0x14003ad98  lea     rcx, [rsi+8]; this
0x14003ad9c  call    ?Terminate@CClipServer@@MEAAJXZ; CClipServer::Terminate(void)
0x14003ada1  test    r15d, r15d
0x14003ada4  js      short loc_14003ADAC
0x14003ada6  call    cs:__imp_OleUninitialize
0x14003adac  add     rsp, 38h
0x14003adb0  pop     r15
0x14003adb2  pop     r14
0x14003adb4  pop     rdi
0x14003adb5  pop     rsi
0x14003adb6  pop     rbp
0x14003adb7  pop     rbx
0x14003adb8  retn
```
