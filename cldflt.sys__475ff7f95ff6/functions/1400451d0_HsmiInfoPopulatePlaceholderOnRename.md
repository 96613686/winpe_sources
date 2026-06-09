# HsmiInfoPopulatePlaceholderOnRename

- ea: `0x1400451d0`
- end: `0x140045404`
- name: `HsmiInfoPopulatePlaceholderOnRename`
- size: `564`
- prototype: `__int64 __fastcall(__int64, struct _FILE_OBJECT *, __int16, struct _FLT_CALLBACK_DATA *)`
- caller_count: `0`
- callee_count: `9`
- tags: `installer_update`

## callees

- `0x140001d00`
- `0x140003c50`
- `0x140007ddc`
- `0x140009300`
- `0x14000c8c0`
- `0x1400451d0`
- `0x14004c6d0`
- `0x14005ac10`
- `0x14005f670`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400453d0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400453d0`
- `FLTMGR!FltReleaseContext` at `0x1400453e4`
- `FLTMGR!FltReleaseContext` at `0x1400453e4`

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
  __int64 StreamHandleContext; // rax
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
    HsmDbgBreakOnStatus(FullFilePath);
    if ( FullFilePath >= 0 )
    {
      StreamHandleContext = HsmpGetStreamHandleContext(a4, v10, a2);
      v5 = (void *)StreamHandleContext;
      if ( StreamHandleContext )
      {
        if ( (v7 & 0x10) != 0 )
        {
          v15 = *(_DWORD **)(StreamHandleContext + 16);
          if ( (v15[7] & 2) != 0 )
          {
            FullFilePath = HsmiQueryFullFilePath(v10, v14, a2, 257, P);
            HsmDbgBreakOnStatus(FullFilePath);
            if ( FullFilePath >= 0 )
            {
              FullFilePath = HsmpAcquireUserRequestRundownProtection(v15, a4);
              HsmDbgBreakOnStatus(FullFilePath);
              if ( FullFilePath >= 0 )
              {
                HsmpRecallInitiatePopulation((_DWORD)v5, (_DWORD)v15, (_DWORD)a2, (_DWORD)a4, (__int64)P, 0);
                HsmpReleaseUserRequestRundownProtection(v15);
                FullFilePath = a4->IoStatus.Status;
                HsmDbgBreakOnStatus(FullFilePath);
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
0x1400451d0  push    rbx
0x1400451d2  push    rbp
0x1400451d3  push    rsi
0x1400451d4  push    rdi
0x1400451d5  push    r12
0x1400451d7  push    r13
0x1400451d9  push    r14
0x1400451db  push    r15
0x1400451dd  sub     rsp, 48h
0x1400451e1  xor     ebx, ebx
0x1400451e3  xor     esi, esi
0x1400451e5  xorps   xmm0, xmm0
0x1400451e8  mov     r13, r9
0x1400451eb  mov     edi, r8d
0x1400451ee  mov     rbp, rdx
0x1400451f1  mov     r12, rcx
0x1400451f4  movups  xmmword ptr [rsp+88h+P], xmm0
0x1400451f9  bt      r8d, 0Ah
0x1400451fe  jnb     loc_1400453C1
0x140045204  mov     r14, [rcx+20h]
0x140045208  xor     r9d, r9d
0x14004520b  xor     r8d, r8d
0x14004520e  call    HsmpSetupContexts
0x140045213  mov     ecx, eax
0x140045215  mov     ebx, eax
0x140045217  call    HsmDbgBreakOnStatus
0x14004521c  test    ebx, ebx
0x14004521e  jns     short loc_140045261
0x140045220  mov     rcx, cs:WPP_GLOBAL_Control
0x140045227  lea     rax, WPP_GLOBAL_Control
0x14004522e  cmp     rcx, rax
0x140045231  jz      loc_1400453C1
0x140045237  mov     edx, [rcx+2Ch]
0x14004523a  test    dl, 1
0x14004523d  jz      loc_1400453C1
0x140045243  mov     dil, 2
0x140045246  cmp     [rcx+29h], dil
0x14004524a  jb      loc_1400453C1
0x140045250  lea     edx, [rsi+0Ch]
0x140045253  mov     dword ptr [rsp+88h+var_60], ebx
0x140045257  mov     [rsp+88h+var_68], rbp
0x14004525c  jmp     loc_1400453AE
0x140045261  mov     r8, rbp; FileObject
0x140045264  mov     rdx, r14; Instance
0x140045267  mov     rcx, r13; CallbackData
0x14004526a  call    HsmpGetStreamHandleContext
0x14004526f  mov     rsi, rax
0x140045272  test    rax, rax
0x140045275  jz      loc_1400453C1
0x14004527b  test    dil, 10h
0x14004527f  jz      loc_1400453C1
0x140045285  mov     r15, [rax+10h]
0x140045289  mov     dil, 2
0x14004528c  mov     ecx, [r15+1Ch]
0x140045290  test    dil, cl
0x140045293  jz      loc_1400453C1
0x140045299  lea     rax, [rsp+88h+P]
0x14004529e  mov     r9d, 101h
0x1400452a4  mov     r8, rbp
0x1400452a7  mov     [rsp+88h+var_68], rax
0x1400452ac  mov     rcx, r14
0x1400452af  call    HsmiQueryFullFilePath
0x1400452b4  mov     ecx, eax
0x1400452b6  mov     ebx, eax
0x1400452b8  call    HsmDbgBreakOnStatus
0x1400452bd  test    ebx, ebx
0x1400452bf  jns     short loc_1400452F7
0x1400452c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400452c8  lea     rax, WPP_GLOBAL_Control
0x1400452cf  cmp     rcx, rax
0x1400452d2  jz      loc_1400453C1
0x1400452d8  mov     eax, [rcx+2Ch]
0x1400452db  test    al, 1
0x1400452dd  jz      loc_1400453C1
0x1400452e3  cmp     [rcx+29h], dil
0x1400452e7  jb      loc_1400453C1
0x1400452ed  mov     edx, 0Dh
0x1400452f2  jmp     loc_140045253
0x1400452f7  mov     rdx, r13; CallbackData
0x1400452fa  mov     rcx, r15; Context
0x1400452fd  call    HsmpAcquireUserRequestRundownProtection
0x140045302  mov     ecx, eax
0x140045304  mov     ebx, eax
0x140045306  call    HsmDbgBreakOnStatus
0x14004530b  test    ebx, ebx
0x14004530d  jns     short loc_140045345
0x14004530f  mov     rcx, cs:WPP_GLOBAL_Control
0x140045316  lea     rax, WPP_GLOBAL_Control
0x14004531d  cmp     rcx, rax
0x140045320  jz      loc_1400453C1
0x140045326  mov     eax, [rcx+2Ch]
0x140045329  test    al, 1
0x14004532b  jz      loc_1400453C1
0x140045331  cmp     [rcx+29h], dil
0x140045335  jb      loc_1400453C1
0x14004533b  mov     edx, 0Eh
0x140045340  jmp     loc_140045253
0x140045345  lea     rax, [rsp+88h+P]
0x14004534a  mov     [rsp+88h+var_60], 0
0x140045353  mov     r9, r13
0x140045356  mov     [rsp+88h+var_68], rax
0x14004535b  mov     r8, rbp
0x14004535e  mov     rdx, r15
0x140045361  mov     rcx, rsi
0x140045364  call    HsmpRecallInitiatePopulation
0x140045369  mov     rcx, r15; Context
0x14004536c  call    HsmpReleaseUserRequestRundownProtection
0x140045371  mov     ebx, [r13+18h]
0x140045375  mov     ecx, ebx
0x140045377  call    HsmDbgBreakOnStatus
0x14004537c  test    ebx, ebx
0x14004537e  jns     short loc_1400453C1
0x140045380  mov     rcx, cs:WPP_GLOBAL_Control
0x140045387  lea     rax, WPP_GLOBAL_Control
0x14004538e  cmp     rcx, rax
0x140045391  jz      short loc_1400453C1
0x140045393  mov     eax, [rcx+2Ch]
0x140045396  test    al, 1
0x140045398  jz      short loc_1400453C1
0x14004539a  cmp     [rcx+29h], dil
0x14004539e  jb      short loc_1400453C1
0x1400453a0  mov     dword ptr [rsp+88h+var_60], ebx
0x1400453a4  mov     edx, 0Fh
0x1400453a9  mov     [rsp+88h+var_68], r12
0x1400453ae  mov     rcx, [rcx+18h]
0x1400453b2  lea     r8, WPP_e26ac64b2c40307be864d687cc32cd5d_Traceguids
0x1400453b9  mov     r9, r14
0x1400453bc  call    WPP_SF_qqd
0x1400453c1  mov     rcx, [rsp+88h+P+8]; P
0x1400453c6  test    rcx, rcx
0x1400453c9  jz      short loc_1400453DC
0x1400453cb  mov     edx, 73557348h; Tag
0x1400453d0  call    cs:__imp_ExFreePoolWithTag
0x1400453d7  nop     dword ptr [rax+rax+00h]
0x1400453dc  test    rsi, rsi
0x1400453df  jz      short loc_1400453F0
0x1400453e1  mov     rcx, rsi; Context
0x1400453e4  call    cs:__imp_FltReleaseContext
0x1400453eb  nop     dword ptr [rax+rax+00h]
0x1400453f0  mov     eax, ebx
0x1400453f2  add     rsp, 48h
0x1400453f6  pop     r15
0x1400453f8  pop     r14
0x1400453fa  pop     r13
0x1400453fc  pop     r12
0x1400453fe  pop     rdi
0x1400453ff  pop     rsi
0x140045400  pop     rbp
0x140045401  pop     rbx
0x140045402  retn
```
