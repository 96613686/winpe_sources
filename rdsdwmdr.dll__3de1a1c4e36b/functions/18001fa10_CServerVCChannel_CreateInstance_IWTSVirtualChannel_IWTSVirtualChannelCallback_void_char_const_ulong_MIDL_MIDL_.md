# CServerVCChannel::CreateInstance(IWTSVirtualChannel * *,IWTSVirtualChannelCallback *,void *,char const *,ulong,__MIDL___MIDL_itf_tscaddon_0000_0007_0001,int,IAPCThread *,ChannelType)

- ea: `0x18001fa10`
- end: `0x18001fb8b`
- name: `?CreateInstance@CServerVCChannel@@SAJPEAPEAUIWTSVirtualChannel@@PEAUIWTSVirtualChannelCallback@@PEAXPEBDKW4__MIDL___MIDL_itf_tscaddon_0000_0007_0001@@HPEAVIAPCThread@@W4ChannelType@@@Z`
- size: `379`
- prototype: `__int64 __fastcall(CServerVCChannel **, __int64, void *, __int64, int, int, int, __int64, int)`
- caller_count: `3`
- callee_count: `8`
- tags: ``

## callers

- `0x18001f820`
- `0x1800209f0`
- `0x180020a40`

## callees

- `0x1800032d4`
- `0x18001d098`
- `0x18001d114`
- `0x18001ef44`
- `0x18001f484`
- `0x18001fa10`
- `0x180020078`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001fb24`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001fb24`

## pseudocode

```c
__int64 __fastcall CServerVCChannel::CreateInstance(
        CServerVCChannel **a1,
        __int64 a2,
        void *a3,
        __int64 a4,
        int a5,
        int a6,
        int a7,
        __int64 a8,
        int a9)
{
  CServerVCChannel *v13; // rax
  CServerVCChannel *v14; // rax
  CServerVCChannel *v15; // rdi
  int v16; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  unsigned int v18; // eax
  __int64 v20; // [rsp+28h] [rbp-50h]

  v13 = (CServerVCChannel *)operator new(0x1B8u);
  if ( v13 && (v14 = CServerVCChannel::CServerVCChannel(v13), (v15 = v14) != 0) )
  {
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v14 + 5) + 8LL))(*((_QWORD *)v14 + 5));
    v16 = CServerVCChannel::Initialize(v15, a2, a3, a4, a5, a6, a7, a8, a9);
    if ( v16 < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        LODWORD(v20) = v16;
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          11,
          (unsigned int)&WPP_12a54374ce1a3d6eb8f95169a7d52c65_Traceguids,
          CurrentThreadActivityIdPrefix,
          (__int64)"CServerVCChannel::Initialize failed",
          v20);
      }
      goto LABEL_9;
    }
    *a1 = v15;
    if ( v16 )
LABEL_9:
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v15 + 5) + 16LL))(*((_QWORD *)v15 + 5));
  }
  else
  {
    if ( a3 )
      CloseHandle(a3);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v18 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Ds(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        (unsigned int)&WPP_12a54374ce1a3d6eb8f95169a7d52c65_Traceguids,
        v18,
        (__int64)"CServerVCChannel");
    }
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x18001fa10  push    rbx
0x18001fa12  push    rbp
0x18001fa13  push    rsi
0x18001fa14  push    rdi
0x18001fa15  push    r14
0x18001fa17  sub     rsp, 50h
0x18001fa1b  mov     rsi, rcx
0x18001fa1e  mov     rbp, r9
0x18001fa21  mov     ecx, 1B8h; Size
0x18001fa26  mov     rbx, r8
0x18001fa29  mov     r14, rdx
0x18001fa2c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001fa31  test    rax, rax
0x18001fa34  jz      loc_18001FB1C
0x18001fa3a  mov     rcx, rax; this
0x18001fa3d  call    ??0CServerVCChannel@@QEAA@XZ; CServerVCChannel::CServerVCChannel(void)
0x18001fa42  mov     rdi, rax
0x18001fa45  test    rax, rax
0x18001fa48  jz      loc_18001FB1C
0x18001fa4e  mov     rcx, [rax+28h]
0x18001fa52  mov     rdx, [rcx]
0x18001fa55  mov     rax, [rdx+8]
0x18001fa59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fa5e  mov     eax, [rsp+78h+arg_30]
0x18001fa65  mov     r9, rbp
0x18001fa68  mov     ecx, [rsp+78h+arg_40]
0x18001fa6f  mov     r8, rbx
0x18001fa72  mov     [rsp+78h+var_38], ecx
0x18001fa76  mov     rdx, r14
0x18001fa79  mov     rcx, [rsp+78h+arg_38]
0x18001fa81  mov     [rsp+78h+var_40], rcx
0x18001fa86  mov     rcx, rdi
0x18001fa89  mov     [rsp+78h+var_48], eax
0x18001fa8d  mov     eax, [rsp+78h+arg_28]
0x18001fa94  mov     dword ptr [rsp+78h+var_50], eax
0x18001fa98  mov     eax, [rsp+78h+arg_20]
0x18001fa9f  mov     dword ptr [rsp+78h+var_58], eax
0x18001faa3  call    ?Initialize@CServerVCChannel@@QEAAJPEAUIWTSVirtualChannelCallback@@PEAXPEBDKW4__MIDL___MIDL_itf_tscaddon_0000_0007_0001@@HPEAVIAPCThread@@W4ChannelType@@@Z; CServerVCChannel::Initialize(IWTSVirtualChannelCallback *,void *,char const *,ulong,__MIDL___MIDL_itf_tscaddon_0000_0007_0001,int,IAPCThread *,ChannelType)
0x18001faa8  mov     ebx, eax
0x18001faaa  test    eax, eax
0x18001faac  jns     short loc_18001FB03
0x18001faae  mov     rax, cs:WPP_GLOBAL_Control
0x18001fab5  lea     rcx, WPP_GLOBAL_Control
0x18001fabc  cmp     rax, rcx
0x18001fabf  jz      short loc_18001FB0A
0x18001fac1  test    byte ptr [rax+1Ch], 8
0x18001fac5  jz      short loc_18001FB0A
0x18001fac7  cmp     byte ptr [rax+19h], 2
0x18001facb  jb      short loc_18001FB0A
0x18001facd  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18001fad2  lea     rcx, aCservervcchann_3; "CServerVCChannel::Initialize failed"
0x18001fad9  mov     dword ptr [rsp+78h+var_50], ebx
0x18001fadd  mov     [rsp+78h+var_58], rcx
0x18001fae2  lea     r8, WPP_12a54374ce1a3d6eb8f95169a7d52c65_Traceguids
0x18001fae9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001faf0  mov     edx, 0Bh
0x18001faf5  mov     r9d, eax
0x18001faf8  mov     rcx, [rcx+10h]
0x18001fafc  call    WPP_SF_DsD
0x18001fb01  jmp     short loc_18001FB0A
0x18001fb03  mov     [rsi], rdi
0x18001fb06  test    ebx, ebx
0x18001fb08  jz      short loc_18001FB7E
0x18001fb0a  mov     rcx, [rdi+28h]
0x18001fb0e  mov     rax, [rcx]
0x18001fb11  mov     rax, [rax+10h]
0x18001fb15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fb1a  jmp     short loc_18001FB7E
0x18001fb1c  test    rbx, rbx
0x18001fb1f  jz      short loc_18001FB2A
0x18001fb21  mov     rcx, rbx; hObject
0x18001fb24  call    cs:__imp_CloseHandle
0x18001fb2a  mov     rax, cs:WPP_GLOBAL_Control
0x18001fb31  lea     rcx, WPP_GLOBAL_Control
0x18001fb38  cmp     rax, rcx
0x18001fb3b  jz      short loc_18001FB79
0x18001fb3d  test    byte ptr [rax+1Ch], 8
0x18001fb41  jz      short loc_18001FB79
0x18001fb43  cmp     byte ptr [rax+19h], 2
0x18001fb47  jb      short loc_18001FB79
0x18001fb49  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18001fb4e  lea     rcx, aCservervcchann_4; "CServerVCChannel"
0x18001fb55  mov     edx, 0Ah
0x18001fb5a  mov     [rsp+78h+var_58], rcx
0x18001fb5f  lea     r8, WPP_12a54374ce1a3d6eb8f95169a7d52c65_Traceguids
0x18001fb66  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fb6d  mov     r9d, eax
0x18001fb70  mov     rcx, [rcx+10h]
0x18001fb74  call    WPP_SF_Ds
0x18001fb79  mov     ebx, 8007000Eh
0x18001fb7e  mov     eax, ebx
0x18001fb80  add     rsp, 50h
0x18001fb84  pop     r14
0x18001fb86  pop     rdi
0x18001fb87  pop     rsi
0x18001fb88  pop     rbp
0x18001fb89  pop     rbx
0x18001fb8a  retn
```
