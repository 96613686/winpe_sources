# CAPCThread::CreateInstance(IAPCThread * *)

- ea: `0x18001f870`
- end: `0x18001fa09`
- name: `?CreateInstance@CAPCThread@@SAJPEAPEAVIAPCThread@@@Z`
- size: `409`
- prototype: `__int64 __fastcall(struct IAPCThread **)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800205c0`

## callees

- `0x1800032d4`
- `0x18001d098`
- `0x18001d114`
- `0x18001ef44`
- `0x18001f870`
- `0x18001fe90`
- `0x18002c010`

## string_xrefs

- `0x18001f8a6`: `CAPCThread`
- `0x18001f9ce`: `CAPCThread`
- `0x18001f959`: `CAPCThread::Initialize failed`

## pseudocode

```c
__int64 __fastcall CAPCThread::CreateInstance(struct IAPCThread **a1)
{
  _DWORD *v2; // rax
  _DWORD *v3; // rbx
  int v4; // edi
  unsigned int CurrentThreadActivityIdPrefix; // eax
  unsigned int v6; // eax

  v2 = operator new(0x50u);
  v3 = v2;
  if ( v2 )
  {
    *(_QWORD *)v2 = &IAPCThread::`vftable';
    v2[8] = -607474739;
    *((_QWORD *)v2 + 3) = "CAPCThread";
    v2[9] = 1;
    *((_QWORD *)v2 + 1) = &CServerVCChannel::`vftable'{for `INonDelegatingUnknown'};
    *((_QWORD *)v2 + 2) = &CTSUnknown::`vftable'{for `CTSObject'};
    v2[12] = 0;
    *((_QWORD *)v2 + 5) = v2 + 2;
    *(_QWORD *)v2 = &CAPCThread::`vftable';
    *((_QWORD *)v2 + 1) = &CServerVCChannel::`vftable'{for `INonDelegatingUnknown'};
    *((_QWORD *)v2 + 2) = &CAPCThread::`vftable'{for `CTSObject'};
    *((_QWORD *)v2 + 7) = 0;
    *((_QWORD *)v2 + 8) = 0;
    *((_QWORD *)v2 + 9) = 0;
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v2 + 5) + 8LL))(*((_QWORD *)v2 + 5));
    v4 = CAPCThread::Initialize((CAPCThread *)(v3 + 4));
    if ( v4 < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          11,
          (unsigned int)WPP_e06d9da063383fc2b93c39ab877dcc3d_Traceguids,
          CurrentThreadActivityIdPrefix,
          (__int64)"CAPCThread::Initialize failed",
          v4);
      }
      goto LABEL_8;
    }
    *a1 = (struct IAPCThread *)v3;
    if ( v4 )
LABEL_8:
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v3 + 5) + 16LL))(*((_QWORD *)v3 + 5));
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v6 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Ds(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        (unsigned int)WPP_e06d9da063383fc2b93c39ab877dcc3d_Traceguids,
        v6,
        (__int64)"CAPCThread");
    }
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18001f870  mov     [rsp+arg_0], rbx
0x18001f875  mov     [rsp+arg_8], rsi
0x18001f87a  push    rdi
0x18001f87b  sub     rsp, 30h
0x18001f87f  mov     rsi, rcx
0x18001f882  mov     ecx, 50h ; 'P'; Size
0x18001f887  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001f88c  mov     rbx, rax
0x18001f88f  test    rax, rax
0x18001f892  jz      loc_18001F9A3
0x18001f898  lea     rdx, [rbx+8]
0x18001f89c  lea     rax, ??_7IAPCThread@@6B@; const IAPCThread::`vftable'
0x18001f8a3  mov     [rbx], rax
0x18001f8a6  lea     r8, aCapcthread; "CAPCThread"
0x18001f8ad  mov     dword ptr [rdx+18h], 0DBCAABCDh
0x18001f8b4  lea     rax, ??_7CServerVCChannel@@6BINonDelegatingUnknown@@@; const CServerVCChannel::`vftable'{for `INonDelegatingUnknown'}
0x18001f8bb  mov     [rdx+10h], r8
0x18001f8bf  mov     dword ptr [rdx+1Ch], 1
0x18001f8c6  mov     [rdx], rax
0x18001f8c9  lea     rax, ??_7CTSUnknown@@6BCTSObject@@@; const CTSUnknown::`vftable'{for `CTSObject'}
0x18001f8d0  mov     [rdx+8], rax
0x18001f8d4  lea     rax, ??_7CAPCThread@@6B@; const CAPCThread::`vftable'
0x18001f8db  mov     dword ptr [rdx+28h], 0
0x18001f8e2  mov     [rdx+20h], rdx
0x18001f8e6  mov     [rbx], rax
0x18001f8e9  lea     rax, ??_7CServerVCChannel@@6BINonDelegatingUnknown@@@; const CServerVCChannel::`vftable'{for `INonDelegatingUnknown'}
0x18001f8f0  mov     [rdx], rax
0x18001f8f3  lea     rax, ??_7CAPCThread@@6BCTSObject@@@; const CAPCThread::`vftable'{for `CTSObject'}
0x18001f8fa  mov     [rbx+10h], rax
0x18001f8fe  mov     qword ptr [rbx+38h], 0
0x18001f906  mov     qword ptr [rbx+40h], 0
0x18001f90e  mov     qword ptr [rbx+48h], 0
0x18001f916  mov     rcx, [rbx+28h]
0x18001f91a  mov     rax, [rcx]
0x18001f91d  mov     rax, [rax+8]
0x18001f921  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f926  lea     rcx, [rbx+10h]; this
0x18001f92a  call    ?Initialize@CAPCThread@@UEAAJXZ; CAPCThread::Initialize(void)
0x18001f92f  mov     edi, eax
0x18001f931  test    eax, eax
0x18001f933  jns     short loc_18001F98A
0x18001f935  mov     rax, cs:WPP_GLOBAL_Control
0x18001f93c  lea     rcx, WPP_GLOBAL_Control
0x18001f943  cmp     rax, rcx
0x18001f946  jz      short loc_18001F991
0x18001f948  test    byte ptr [rax+1Ch], 8
0x18001f94c  jz      short loc_18001F991
0x18001f94e  cmp     byte ptr [rax+19h], 2
0x18001f952  jb      short loc_18001F991
0x18001f954  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18001f959  lea     rcx, aCapcthreadInit; "CAPCThread::Initialize failed"
0x18001f960  mov     [rsp+38h+var_10], edi
0x18001f964  mov     [rsp+38h+var_18], rcx
0x18001f969  lea     r8, WPP_e06d9da063383fc2b93c39ab877dcc3d_Traceguids
0x18001f970  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f977  mov     edx, 0Bh
0x18001f97c  mov     r9d, eax
0x18001f97f  mov     rcx, [rcx+10h]
0x18001f983  call    WPP_SF_DsD
0x18001f988  jmp     short loc_18001F991
0x18001f98a  mov     [rsi], rbx
0x18001f98d  test    edi, edi
0x18001f98f  jz      short loc_18001F9F7
0x18001f991  mov     rcx, [rbx+28h]
0x18001f995  mov     rax, [rcx]
0x18001f998  mov     rax, [rax+10h]
0x18001f99c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f9a1  jmp     short loc_18001F9F7
0x18001f9a3  mov     rax, cs:WPP_GLOBAL_Control
0x18001f9aa  lea     rcx, WPP_GLOBAL_Control
0x18001f9b1  cmp     rax, rcx
0x18001f9b4  jz      short loc_18001F9F2
0x18001f9b6  test    byte ptr [rax+1Ch], 8
0x18001f9ba  jz      short loc_18001F9F2
0x18001f9bc  cmp     byte ptr [rax+19h], 2
0x18001f9c0  jb      short loc_18001F9F2
0x18001f9c2  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18001f9c7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f9ce  lea     r8, aCapcthread; "CAPCThread"
0x18001f9d5  mov     [rsp+38h+var_18], r8
0x18001f9da  mov     edx, 0Ah
0x18001f9df  mov     r9d, eax
0x18001f9e2  lea     r8, WPP_e06d9da063383fc2b93c39ab877dcc3d_Traceguids
0x18001f9e9  mov     rcx, [rcx+10h]
0x18001f9ed  call    WPP_SF_Ds
0x18001f9f2  mov     edi, 8007000Eh
0x18001f9f7  mov     rbx, [rsp+38h+arg_0]
0x18001f9fc  mov     eax, edi
0x18001f9fe  mov     rsi, [rsp+38h+arg_8]
0x18001fa03  add     rsp, 30h
0x18001fa07  pop     rdi
0x18001fa08  retn
```
