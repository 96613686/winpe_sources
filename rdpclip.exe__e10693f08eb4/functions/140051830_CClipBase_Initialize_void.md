# CClipBase::Initialize(void)

- ea: `0x140051830`
- end: `0x140051c21`
- name: `?Initialize@CClipBase@@MEAAJXZ`
- size: `1009`
- prototype: `__int64 __fastcall(CClipBase *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config`

## callers

- `0x14003bdd0`

## callees

- `0x140004b1c`
- `0x1400056c4`
- `0x140005704`
- `0x140005750`
- `0x1400457d4`
- `0x140047dcc`
- `0x14004ad40`
- `0x14004f8ec`
- `0x1400501a8`
- `0x140051830`
- `0x140051c28`
- `0x1400600a8`
- `0x140064154`
- `0x14006b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x140051b92`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x140051b92`

## string_xrefs

- `0x140051973`: `CSimpleDataObject::CreateInstance failed!`
- `0x140051904`: `RdpEdpPolicyManager::CreateInstance failed!`
- `0x140051a70`: `CreateDataChannelEvents failed!`
- `0x140051a28`: `CreateGetDataEvents failed!`
- `0x140051b2c`: `CProxyDataObjectManager::CreateInstance failed!`
- `0x140051acf`: `CProxyStreamManager::CreateInstance failed!`
- `0x140051b7c`: `CDataChannelManager::CreateInstance failed!`

## pseudocode

```c
__int64 __fastcall CClipBase::Initialize(CClipBase *this)
{
  int DataEvents; // ebx
  unsigned int v3; // eax
  int v4; // edx
  const char *v5; // rcx
  int Instance; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  unsigned int v8; // eax
  __int64 v10; // [rsp+28h] [rbp-20h]

  *((_DWORD *)this + 5) |= 2u;
  DataEvents = CLegacyClipboardApi::Initialize((CClipBase *)((char *)this + 792));
  if ( DataEvents >= 0 )
  {
    Instance = RdpEdpPolicyManager::CreateInstance((struct RdpEdpPolicyManager **)this + 101);
    if ( Instance < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        22,
        (unsigned int)&WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids,
        CurrentThreadActivityIdPrefix,
        (__int64)"RdpEdpPolicyManager::CreateInstance failed!",
        Instance);
    }
    DataEvents = CSimpleDataObject::CreateInstance((struct IDataObject **)this + 102);
    if ( DataEvents >= 0 )
    {
      *((_QWORD *)this + 27) = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 83) + 48LL))(*((_QWORD *)this + 83));
      if ( *((_DWORD *)this + 194) )
      {
        DataEvents = CClipBase::CreateGetDataEvents((CClipBase *)((char *)this - 8));
        if ( DataEvents >= 0 )
        {
          DataEvents = CClipBase::CreateDataChannelEvents((CClipBase *)((char *)this - 8));
          if ( DataEvents >= 0 )
          {
            DataEvents = CProxyStreamManager::CreateInstance(
                           (struct IStreamDataAcquire *)(((unsigned __int64)this + 48)
                                                       & -(__int64)(this != (CClipBase *)8)),
                           (struct CProxyStreamManager **)this + 34);
            if ( DataEvents >= 0 )
            {
              DataEvents = CProxyDataObjectManager::CreateInstance(
                             (struct IFormatDataAcquire *)(((unsigned __int64)this + 40)
                                                         & -(__int64)(this != (CClipBase *)8)),
                             *((struct CProxyStreamManager **)this + 34),
                             (struct CProxyDataObjectManager **)this + 33);
              if ( DataEvents >= 0 )
              {
                DataEvents = CDataChannelManager::CreateInstance((struct CDataChannelManager **)this + 105);
                if ( DataEvents >= 0 )
                {
                  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 704));
                  *((_DWORD *)this + 174) = 1;
                  return 0;
                }
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  v3 = RdpWppGetCurrentThreadActivityIdPrefix();
                  v4 = 29;
                  v5 = "CDataChannelManager::CreateInstance failed!";
                  goto LABEL_6;
                }
              }
              else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                     && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                     && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v3 = RdpWppGetCurrentThreadActivityIdPrefix();
                v4 = 28;
                v5 = "CProxyDataObjectManager::CreateInstance failed!";
                goto LABEL_6;
              }
            }
            else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                   && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                   && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v3 = RdpWppGetCurrentThreadActivityIdPrefix();
              v4 = 27;
              v5 = "CProxyStreamManager::CreateInstance failed!";
              goto LABEL_6;
            }
          }
          else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v3 = RdpWppGetCurrentThreadActivityIdPrefix();
            v4 = 26;
            v5 = "CreateDataChannelEvents failed!";
            goto LABEL_6;
          }
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
               && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v3 = RdpWppGetCurrentThreadActivityIdPrefix();
          v4 = 25;
          v5 = "CreateGetDataEvents failed!";
          goto LABEL_6;
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v8 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids, v8);
        }
        return (unsigned int)-2147467259;
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v3 = RdpWppGetCurrentThreadActivityIdPrefix();
      v4 = 23;
      v5 = "CSimpleDataObject::CreateInstance failed!";
      goto LABEL_6;
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v3 = RdpWppGetCurrentThreadActivityIdPrefix();
    v4 = 21;
    v5 = "Initialization of legacy API wrapper failed!";
LABEL_6:
    LODWORD(v10) = DataEvents;
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v4,
      (unsigned int)&WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids,
      v3,
      (__int64)v5,
      v10);
  }
  return (unsigned int)DataEvents;
}

```

## disassembly

```asm
0x140051830  mov     [rsp+arg_10], rbx
0x140051835  mov     [rsp+arg_18], rsi
0x14005183a  mov     [rsp+arg_0], rcx
0x14005183f  push    rdi
0x140051840  push    r12
0x140051842  push    r15
0x140051844  sub     rsp, 30h
0x140051848  mov     rdi, rcx
0x14005184b  or      dword ptr [rcx+14h], 2
0x14005184f  add     rcx, 318h; this
0x140051856  call    ?Initialize@CLegacyClipboardApi@@QEAAJXZ; CLegacyClipboardApi::Initialize(void)
0x14005185b  mov     ebx, eax
0x14005185d  test    eax, eax
0x14005185f  jns     short loc_1400518C5
0x140051861  lea     rsi, WPP_GLOBAL_Control
0x140051868  mov     rax, cs:WPP_GLOBAL_Control
0x14005186f  cmp     rax, rsi
0x140051872  jz      loc_140051C0B
0x140051878  test    byte ptr [rax+1Ch], 8
0x14005187c  jz      loc_140051C0B
0x140051882  cmp     byte ptr [rax+19h], 2
0x140051886  jb      loc_140051C0B
0x14005188c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140051891  mov     edx, 15h
0x140051896  lea     rcx, aInitialization_0; "Initialization of legacy API wrapper fa"...
0x14005189d  mov     dword ptr [rsp+48h+var_20], ebx
0x1400518a1  mov     [rsp+48h+var_28], rcx
0x1400518a6  mov     r9d, eax
0x1400518a9  lea     r8, WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids
0x1400518b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400518b7  mov     rcx, [rcx+10h]
0x1400518bb  call    WPP_SF_DsD
0x1400518c0  jmp     loc_140051C0B
0x1400518c5  lea     rcx, [rdi+328h]; struct RdpEdpPolicyManager **
0x1400518cc  call    ?CreateInstance@RdpEdpPolicyManager@@SAJPEAPEAV1@@Z; RdpEdpPolicyManager::CreateInstance(RdpEdpPolicyManager * *)
0x1400518d1  mov     ebx, eax
0x1400518d3  test    eax, eax
0x1400518d5  jns     short loc_14005192C
0x1400518d7  lea     rsi, WPP_GLOBAL_Control
0x1400518de  mov     rcx, cs:WPP_GLOBAL_Control
0x1400518e5  cmp     rcx, rsi
0x1400518e8  jz      short loc_140051933
0x1400518ea  test    byte ptr [rcx+1Ch], 8
0x1400518ee  jz      short loc_140051933
0x1400518f0  cmp     byte ptr [rcx+19h], 2
0x1400518f4  jb      short loc_140051933
0x1400518f6  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400518fb  mov     edx, 16h
0x140051900  mov     dword ptr [rsp+48h+var_20], ebx
0x140051904  lea     rcx, aRdpedppolicyma; "RdpEdpPolicyManager::CreateInstance fai"...
0x14005190b  mov     [rsp+48h+var_28], rcx
0x140051910  mov     r9d, eax
0x140051913  lea     r8, WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids
0x14005191a  mov     rcx, cs:WPP_GLOBAL_Control
0x140051921  mov     rcx, [rcx+10h]
0x140051925  call    WPP_SF_DsD
0x14005192a  jmp     short loc_140051933
0x14005192c  lea     rsi, WPP_GLOBAL_Control
0x140051933  lea     rcx, [rdi+330h]; struct IDataObject **
0x14005193a  call    ?CreateInstance@CSimpleDataObject@@SAJPEAPEAUIDataObject@@@Z; CSimpleDataObject::CreateInstance(IDataObject * *)
0x14005193f  mov     ebx, eax
0x140051941  test    eax, eax
0x140051943  jns     short loc_14005197F
0x140051945  mov     rax, cs:WPP_GLOBAL_Control
0x14005194c  cmp     rax, rsi
0x14005194f  jz      loc_140051C0B
0x140051955  test    byte ptr [rax+1Ch], 8
0x140051959  jz      loc_140051C0B
0x14005195f  cmp     byte ptr [rax+19h], 2
0x140051963  jb      loc_140051C0B
0x140051969  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005196e  mov     edx, 17h
0x140051973  lea     rcx, aCsimpledataobj; "CSimpleDataObject::CreateInstance faile"...
0x14005197a  jmp     loc_14005189D
0x14005197f  lea     r15, [rdi-8]
0x140051983  mov     rcx, [r15+2A0h]
0x14005198a  mov     rax, [rcx]
0x14005198d  mov     rax, [rax+30h]
0x140051991  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140051996  mov     [rdi+0D8h], rax
0x14005199d  cmp     dword ptr [rdi+308h], 0
0x1400519a4  jnz     short loc_1400519EC
0x1400519a6  mov     rax, cs:WPP_GLOBAL_Control
0x1400519ad  cmp     rax, rsi
0x1400519b0  jz      short loc_1400519E2
0x1400519b2  test    byte ptr [rax+1Ch], 1
0x1400519b6  jz      short loc_1400519E2
0x1400519b8  cmp     byte ptr [rax+19h], 2
0x1400519bc  jb      short loc_1400519E2
0x1400519be  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400519c3  mov     edx, 18h
0x1400519c8  mov     r9d, eax
0x1400519cb  lea     r8, WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids
0x1400519d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400519d9  mov     rcx, [rcx+10h]
0x1400519dd  call    WPP_SF_d
0x1400519e2  mov     ebx, 80004005h
0x1400519e7  jmp     loc_140051C0B
0x1400519ec  mov     rcx, r15; this
0x1400519ef  call    ?CreateGetDataEvents@CClipBase@@AEAAJXZ; CClipBase::CreateGetDataEvents(void)
0x1400519f4  mov     ebx, eax
0x1400519f6  test    eax, eax
0x1400519f8  jns     short loc_140051A34
0x1400519fa  mov     rax, cs:WPP_GLOBAL_Control
0x140051a01  cmp     rax, rsi
0x140051a04  jz      loc_140051C0B
0x140051a0a  test    byte ptr [rax+1Ch], 8
0x140051a0e  jz      loc_140051C0B
0x140051a14  cmp     byte ptr [rax+19h], 2
0x140051a18  jb      loc_140051C0B
0x140051a1e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140051a23  mov     edx, 19h
0x140051a28  lea     rcx, aCreategetdatae; "CreateGetDataEvents failed!"
0x140051a2f  jmp     loc_14005189D
0x140051a34  mov     rcx, r15; this
0x140051a37  call    ?CreateDataChannelEvents@CClipBase@@AEAAJXZ; CClipBase::CreateDataChannelEvents(void)
0x140051a3c  mov     ebx, eax
0x140051a3e  test    eax, eax
0x140051a40  jns     short loc_140051A7C
0x140051a42  mov     rax, cs:WPP_GLOBAL_Control
0x140051a49  cmp     rax, rsi
0x140051a4c  jz      loc_140051C0B
0x140051a52  test    byte ptr [rax+1Ch], 8
0x140051a56  jz      loc_140051C0B
0x140051a5c  cmp     byte ptr [rax+19h], 2
0x140051a60  jb      loc_140051C0B
0x140051a66  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140051a6b  mov     edx, 1Ah
0x140051a70  lea     rcx, aCreatedatachan; "CreateDataChannelEvents failed!"
0x140051a77  jmp     loc_14005189D
0x140051a7c  lea     r12, [rdi+110h]
0x140051a83  mov     rax, r15
0x140051a86  lea     rdx, [rdi+30h]
0x140051a8a  neg     rax
0x140051a8d  sbb     rcx, rcx
0x140051a90  and     rcx, rdx; struct IStreamDataAcquire *
0x140051a93  mov     rdx, r12; struct CProxyStreamManager **
0x140051a96  call    ?CreateInstance@CProxyStreamManager@@SAJPEAVIStreamDataAcquire@@PEAPEAV1@@Z; CProxyStreamManager::CreateInstance(IStreamDataAcquire *,CProxyStreamManager * *)
0x140051a9b  mov     ebx, eax
0x140051a9d  test    eax, eax
0x140051a9f  jns     short loc_140051ADB
0x140051aa1  mov     rax, cs:WPP_GLOBAL_Control
0x140051aa8  cmp     rax, rsi
0x140051aab  jz      loc_140051C0B
0x140051ab1  test    byte ptr [rax+1Ch], 8
0x140051ab5  jz      loc_140051C0B
0x140051abb  cmp     byte ptr [rax+19h], 2
0x140051abf  jb      loc_140051C0B
0x140051ac5  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140051aca  mov     edx, 1Bh
0x140051acf  lea     rcx, aCproxystreamma; "CProxyStreamManager::CreateInstance fai"...
0x140051ad6  jmp     loc_14005189D
0x140051adb  lea     r8, [rdi+108h]; struct CProxyDataObjectManager **
0x140051ae2  lea     rax, [rdi+28h]
0x140051ae6  neg     r15
0x140051ae9  sbb     rcx, rcx
0x140051aec  and     rcx, rax; struct IFormatDataAcquire *
0x140051aef  mov     rdx, [r12]; struct CProxyStreamManager *
0x140051af3  call    ?CreateInstance@CProxyDataObjectManager@@SAJPEAVIFormatDataAcquire@@PEAVCProxyStreamManager@@PEAPEAV1@@Z; CProxyDataObjectManager::CreateInstance(IFormatDataAcquire *,CProxyStreamManager *,CProxyDataObjectManager * *)
0x140051af8  mov     ebx, eax
0x140051afa  test    eax, eax
0x140051afc  jns     short loc_140051B38
0x140051afe  mov     rax, cs:WPP_GLOBAL_Control
0x140051b05  cmp     rax, rsi
0x140051b08  jz      loc_140051C0B
0x140051b0e  test    byte ptr [rax+1Ch], 8
0x140051b12  jz      loc_140051C0B
0x140051b18  cmp     byte ptr [rax+19h], 2
0x140051b1c  jb      loc_140051C0B
0x140051b22  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140051b27  mov     edx, 1Ch
0x140051b2c  lea     rcx, aCproxydataobje_1; "CProxyDataObjectManager::CreateInstance"...
0x140051b33  jmp     loc_14005189D
0x140051b38  lea     rcx, [rdi+348h]; struct CDataChannelManager **
0x140051b3f  call    ?CreateInstance@CDataChannelManager@@SAJPEAPEAV1@@Z; CDataChannelManager::CreateInstance(CDataChannelManager * *)
0x140051b44  mov     ebx, eax
0x140051b46  mov     [rsp+48h+arg_8], eax
0x140051b4a  test    eax, eax
0x140051b4c  jns     short loc_140051B88
0x140051b4e  mov     rax, cs:WPP_GLOBAL_Control
0x140051b55  cmp     rax, rsi
0x140051b58  jz      loc_140051C0B
0x140051b5e  test    byte ptr [rax+1Ch], 8
0x140051b62  jz      loc_140051C0B
0x140051b68  cmp     byte ptr [rax+19h], 2
0x140051b6c  jb      loc_140051C0B
0x140051b72  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140051b77  mov     edx, 1Dh
0x140051b7c  lea     rcx, aCdatachannelma_0; "CDataChannelManager::CreateInstance fai"...
0x140051b83  jmp     loc_14005189D
0x140051b88  xor     r15d, r15d
0x140051b8b  lea     rcx, [rdi+2C0h]; lpCriticalSection
0x140051b92  call    cs:__imp_InitializeCriticalSection
0x140051b98  jmp     short loc_140051BAD
0x140051b9a  mov     r15d, eax
0x140051b9d  lea     rsi, WPP_GLOBAL_Control
0x140051ba4  mov     rdi, [rsp+48h+arg_0]
0x140051ba9  mov     ebx, [rsp+48h+arg_8]
0x140051bad  test    r15d, r15d
0x140051bb0  jnz     short loc_140051BC0
0x140051bb2  mov     dword ptr [rdi+2B8h], 1
0x140051bbc  xor     ebx, ebx
0x140051bbe  jmp     short loc_140051C0B
0x140051bc0  mov     dword ptr [rdi+2B8h], 0
0x140051bca  mov     rax, cs:WPP_GLOBAL_Control
0x140051bd1  cmp     rax, rsi
0x140051bd4  jz      short loc_140051C0B
0x140051bd6  test    byte ptr [rax+1Ch], 1
0x140051bda  jz      short loc_140051C0B
0x140051bdc  cmp     byte ptr [rax+19h], 2
0x140051be0  jb      short loc_140051C0B
0x140051be2  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140051be7  mov     edx, 1Eh
0x140051bec  mov     dword ptr [rsp+48h+var_28], r15d
0x140051bf1  mov     r9d, eax
0x140051bf4  lea     r8, WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids
0x140051bfb  mov     rcx, cs:WPP_GLOBAL_Control
0x140051c02  mov     rcx, [rcx+10h]
0x140051c06  call    WPP_SF_Dd
0x140051c0b  mov     eax, ebx
0x140051c0d  mov     rbx, [rsp+48h+arg_10]
0x140051c12  mov     rsi, [rsp+48h+arg_18]
0x140051c17  add     rsp, 30h
0x140051c1b  pop     r15
0x140051c1d  pop     r12
0x140051c1f  pop     rdi
0x140051c20  retn
```
