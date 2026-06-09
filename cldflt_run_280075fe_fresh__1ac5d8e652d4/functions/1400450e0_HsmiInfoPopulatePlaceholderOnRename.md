# HsmiInfoPopulatePlaceholderOnRename

- ea: `0x1400450e0`
- end: `0x140045314`
- name: `HsmiInfoPopulatePlaceholderOnRename`
- size: `564`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `installer_update`

## callees

- `0x140001d00`
- `0x140003c50`
- `0x140007ddc`
- `0x140009300`
- `0x14000c8c0`
- `0x1400450e0`
- `0x14004c5e0`
- `0x14005aaf0`
- `0x14005f550`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400452e0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400452e0`
- `FLTMGR!FltReleaseContext` at `0x1400452f4`
- `FLTMGR!FltReleaseContext` at `0x1400452f4`

## pseudocode

```c
__int64 __fastcall HsmiInfoPopulatePlaceholderOnRename(
        __int64 a1,
        struct _FILE_OBJECT *a2,
        __int16 a3,
        struct _FLT_CALLBACK_DATA *a4)
{
  int FullFilePath; // ebx
  void *v5; // rsi
  char v7; // di
  struct _FLT_INSTANCE *v10; // r14
  PDEVICE_OBJECT v11; // rcx
  __int64 v12; // rdx
  PFLT_CONTEXT StreamHandleContext; // rax
  __int64 v14; // rdx
  _DWORD *v15; // r15
  PVOID P[2]; // [rsp+30h] [rbp-58h] BYREF

  FullFilePath = 0;
  v5 = 0;
  v7 = a3;
  *(_OWORD *)P = 0;
  if ( (a3 & 0x400) != 0 )
  {
    v10 = *(struct _FLT_INSTANCE **)(a1 + 32);
    FullFilePath = HsmpSetupContexts(a1, a2, 0, 0);
    HsmDbgBreakOnStatus((unsigned int)FullFilePath);
    if ( FullFilePath >= 0 )
    {
      StreamHandleContext = HsmpGetStreamHandleContext(a4, v10, a2);
      v5 = StreamHandleContext;
      if ( StreamHandleContext )
      {
        if ( (v7 & 0x10) != 0 )
        {
          v15 = (_DWORD *)*((_QWORD *)StreamHandleContext + 2);
          if ( (v15[7] & 2) != 0 )
          {
            FullFilePath = HsmiQueryFullFilePath((__int64)v10, v14, a2, 0x101u, P);
            HsmDbgBreakOnStatus((unsigned int)FullFilePath);
            if ( FullFilePath >= 0 )
            {
              FullFilePath = HsmpAcquireUserRequestRundownProtection(v15, a4);
              HsmDbgBreakOnStatus((unsigned int)FullFilePath);
              if ( FullFilePath >= 0 )
              {
                HsmpRecallInitiatePopulation((_DWORD)v5, (_DWORD)v15, (_DWORD)a2, (_DWORD)a4, (__int64)P, 0);
                HsmpReleaseUserRequestRundownProtection(v15);
                FullFilePath = a4->IoStatus.Status;
                HsmDbgBreakOnStatus((unsigned int)FullFilePath);
                if ( FullFilePath < 0
                  && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                {
                  WPP_SF_qqd(
                    WPP_GLOBAL_Control->AttachedDevice,
                    15,
                    WPP_e26ac64b2c40307be864d687cc32cd5d_Traceguids,
                    v10,
                    a1,
                    FullFilePath);
                }
              }
              else
              {
                v11 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                {
                  v12 = 14;
                  goto LABEL_7;
                }
              }
            }
            else
            {
              v11 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
              {
                v12 = 13;
                goto LABEL_7;
              }
            }
          }
        }
      }
    }
    else
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v12 = 12;
LABEL_7:
        WPP_SF_qqd(v11->AttachedDevice, v12, WPP_e26ac64b2c40307be864d687cc32cd5d_Traceguids, v10, a2, FullFilePath);
      }
    }
  }
  if ( P[1] )
    ExFreePoolWithTag(P[1], 0x73557348u);
  if ( v5 )
    FltReleaseContext(v5);
  return (unsigned int)FullFilePath;
}

```

## disassembly

```asm
0x1400450e0  push    rbx
0x1400450e2  push    rbp
0x1400450e3  push    rsi
0x1400450e4  push    rdi
0x1400450e5  push    r12
0x1400450e7  push    r13
0x1400450e9  push    r14
0x1400450eb  push    r15
0x1400450ed  sub     rsp, 48h
0x1400450f1  xor     ebx, ebx
0x1400450f3  xor     esi, esi
0x1400450f5  xorps   xmm0, xmm0
0x1400450f8  mov     r13, r9
0x1400450fb  mov     edi, r8d
0x1400450fe  mov     rbp, rdx
0x140045101  mov     r12, rcx
0x140045104  movups  xmmword ptr [rsp+88h+P], xmm0
0x140045109  bt      r8d, 0Ah
0x14004510e  jnb     loc_1400452D1
0x140045114  mov     r14, [rcx+20h]
0x140045118  xor     r9d, r9d
0x14004511b  xor     r8d, r8d
0x14004511e  call    HsmpSetupContexts
0x140045123  mov     ecx, eax
0x140045125  mov     ebx, eax
0x140045127  call    HsmDbgBreakOnStatus
0x14004512c  test    ebx, ebx
0x14004512e  jns     short loc_140045171
0x140045130  mov     rcx, cs:WPP_GLOBAL_Control
0x140045137  lea     rax, WPP_GLOBAL_Control
0x14004513e  cmp     rcx, rax
0x140045141  jz      loc_1400452D1
0x140045147  mov     edx, [rcx+2Ch]
0x14004514a  test    dl, 1
0x14004514d  jz      loc_1400452D1
0x140045153  mov     dil, 2
0x140045156  cmp     [rcx+29h], dil
0x14004515a  jb      loc_1400452D1
0x140045160  lea     edx, [rsi+0Ch]
0x140045163  mov     dword ptr [rsp+88h+var_60], ebx
0x140045167  mov     [rsp+88h+var_68], rbp
0x14004516c  jmp     loc_1400452BE
0x140045171  mov     r8, rbp; FileObject
0x140045174  mov     rdx, r14; Instance
0x140045177  mov     rcx, r13; CallbackData
0x14004517a  call    HsmpGetStreamHandleContext
0x14004517f  mov     rsi, rax
0x140045182  test    rax, rax
0x140045185  jz      loc_1400452D1
0x14004518b  test    dil, 10h
0x14004518f  jz      loc_1400452D1
0x140045195  mov     r15, [rax+10h]
0x140045199  mov     dil, 2
0x14004519c  mov     ecx, [r15+1Ch]
0x1400451a0  test    dil, cl
0x1400451a3  jz      loc_1400452D1
0x1400451a9  lea     rax, [rsp+88h+P]
0x1400451ae  mov     r9d, 101h
0x1400451b4  mov     r8, rbp
0x1400451b7  mov     [rsp+88h+var_68], rax
0x1400451bc  mov     rcx, r14
0x1400451bf  call    HsmiQueryFullFilePath
0x1400451c4  mov     ecx, eax
0x1400451c6  mov     ebx, eax
0x1400451c8  call    HsmDbgBreakOnStatus
0x1400451cd  test    ebx, ebx
0x1400451cf  jns     short loc_140045207
0x1400451d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400451d8  lea     rax, WPP_GLOBAL_Control
0x1400451df  cmp     rcx, rax
0x1400451e2  jz      loc_1400452D1
0x1400451e8  mov     eax, [rcx+2Ch]
0x1400451eb  test    al, 1
0x1400451ed  jz      loc_1400452D1
0x1400451f3  cmp     [rcx+29h], dil
0x1400451f7  jb      loc_1400452D1
0x1400451fd  mov     edx, 0Dh
0x140045202  jmp     loc_140045163
0x140045207  mov     rdx, r13; CallbackData
0x14004520a  mov     rcx, r15; Context
0x14004520d  call    HsmpAcquireUserRequestRundownProtection
0x140045212  mov     ecx, eax
0x140045214  mov     ebx, eax
0x140045216  call    HsmDbgBreakOnStatus
0x14004521b  test    ebx, ebx
0x14004521d  jns     short loc_140045255
0x14004521f  mov     rcx, cs:WPP_GLOBAL_Control
0x140045226  lea     rax, WPP_GLOBAL_Control
0x14004522d  cmp     rcx, rax
0x140045230  jz      loc_1400452D1
0x140045236  mov     eax, [rcx+2Ch]
0x140045239  test    al, 1
0x14004523b  jz      loc_1400452D1
0x140045241  cmp     [rcx+29h], dil
0x140045245  jb      loc_1400452D1
0x14004524b  mov     edx, 0Eh
0x140045250  jmp     loc_140045163
0x140045255  lea     rax, [rsp+88h+P]
0x14004525a  mov     [rsp+88h+var_60], 0
0x140045263  mov     r9, r13
0x140045266  mov     [rsp+88h+var_68], rax
0x14004526b  mov     r8, rbp
0x14004526e  mov     rdx, r15
0x140045271  mov     rcx, rsi
0x140045274  call    HsmpRecallInitiatePopulation
0x140045279  mov     rcx, r15; Context
0x14004527c  call    HsmpReleaseUserRequestRundownProtection
0x140045281  mov     ebx, [r13+18h]
0x140045285  mov     ecx, ebx
0x140045287  call    HsmDbgBreakOnStatus
0x14004528c  test    ebx, ebx
0x14004528e  jns     short loc_1400452D1
0x140045290  mov     rcx, cs:WPP_GLOBAL_Control
0x140045297  lea     rax, WPP_GLOBAL_Control
0x14004529e  cmp     rcx, rax
0x1400452a1  jz      short loc_1400452D1
0x1400452a3  mov     eax, [rcx+2Ch]
0x1400452a6  test    al, 1
0x1400452a8  jz      short loc_1400452D1
0x1400452aa  cmp     [rcx+29h], dil
0x1400452ae  jb      short loc_1400452D1
0x1400452b0  mov     dword ptr [rsp+88h+var_60], ebx
0x1400452b4  mov     edx, 0Fh
0x1400452b9  mov     [rsp+88h+var_68], r12
0x1400452be  mov     rcx, [rcx+18h]
0x1400452c2  lea     r8, WPP_e26ac64b2c40307be864d687cc32cd5d_Traceguids
0x1400452c9  mov     r9, r14
0x1400452cc  call    WPP_SF_qqd
0x1400452d1  mov     rcx, [rsp+88h+P+8]; P
0x1400452d6  test    rcx, rcx
0x1400452d9  jz      short loc_1400452EC
0x1400452db  mov     edx, 73557348h; Tag
0x1400452e0  call    cs:__imp_ExFreePoolWithTag
0x1400452e7  nop     dword ptr [rax+rax+00h]
0x1400452ec  test    rsi, rsi
0x1400452ef  jz      short loc_140045300
0x1400452f1  mov     rcx, rsi; Context
0x1400452f4  call    cs:__imp_FltReleaseContext
0x1400452fb  nop     dword ptr [rax+rax+00h]
0x140045300  mov     eax, ebx
0x140045302  add     rsp, 48h
0x140045306  pop     r15
0x140045308  pop     r14
0x14004530a  pop     r13
0x14004530c  pop     r12
0x14004530e  pop     rdi
0x14004530f  pop     rsi
0x140045310  pop     rbp
0x140045311  pop     rbx
0x140045312  retn
```
