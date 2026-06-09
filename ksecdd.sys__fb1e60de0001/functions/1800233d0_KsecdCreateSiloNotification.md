# KsecdCreateSiloNotification

- ea: `0x1800233d0`
- end: `0x180023680`
- name: `KsecdCreateSiloNotification`
- size: `688`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x180001ec0`
- `0x180007bd8`
- `0x18000c6d0`
- `0x180010a00`
- `0x180010d00`
- `0x18001f448`
- `0x180023244`
- `0x1800233d0`

## import_xrefs

- `ntoskrnl!PsCreateSiloContext` at `0x18002340a`
- `ntoskrnl!PsCreateSiloContext` at `0x18002340a`
- `ntoskrnl!PsIsHostSilo` at `0x18002352d`
- `ntoskrnl!PsIsHostSilo` at `0x18002352d`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x18002355c`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x18002355c`
- `ntoskrnl!PsGetHostSilo` at `0x180023547`
- `ntoskrnl!PsGetHostSilo` at `0x180023571`
- `ntoskrnl!PsGetHostSilo` at `0x180023547`
- `ntoskrnl!PsGetHostSilo` at `0x180023571`
- `ntoskrnl!KeBugCheckEx` at `0x180023594`
- `ntoskrnl!KeBugCheckEx` at `0x180023594`
- `ntoskrnl!PsInsertPermanentSiloContext` at `0x180023621`
- `ntoskrnl!PsInsertPermanentSiloContext` at `0x180023621`
- `ntoskrnl!ExAllocatePool2` at `0x1800235c4`
- `ntoskrnl!ExAllocatePool2` at `0x1800235c4`

## pseudocode

```c
__int64 __fastcall KsecdCreateSiloNotification(__int64 a1)
{
  int inited; // ebx
  _QWORD *v3; // rcx
  __int64 v4; // rdx
  unsigned int v5; // ebx
  __int64 HostSilo; // rax
  ULONG_PTR v7; // rax
  __int64 v8; // rcx
  __int64 Pool2; // rax
  void *v10; // rcx
  struct _KSECDDLSASTATE *v12; // [rsp+48h] [rbp+18h] BYREF
  __int64 v13; // [rsp+50h] [rbp+20h] BYREF

  v12 = 0;
  v13 = 0;
  inited = PsCreateSiloContext(a1, 592, 512, 0, &v12);
  if ( inited >= 0 )
  {
    memset(v12, 0, 0x250u);
    inited = KsecInitAddressValidation(v12);
    if ( inited >= 0 )
    {
      *((_QWORD *)v12 + 65) = 1;
      inited = IoctlIpcInitSilo(v12);
      if ( inited >= 0 )
      {
        inited = KsecPerfCountersInitSilo(v12);
        if ( inited >= 0 )
        {
          if ( !(unsigned __int8)PsIsHostSilo(a1) )
          {
            v5 = KsecddSiloContextSlot;
            HostSilo = PsGetHostSilo();
            PsGetPermanentSiloContext(HostSilo, v5, &v13);
            if ( !v13 )
            {
              v7 = PsGetHostSilo();
              KeBugCheckEx(0x18Au, v7, 0, 0, 0);
            }
            v8 = *(unsigned int *)(v13 + 480);
            *((_DWORD *)v12 + 120) = v8;
            Pool2 = ExAllocatePool2(64, 40 * v8, 1667593035);
            *((_QWORD *)v12 + 59) = Pool2;
            v10 = (void *)*((_QWORD *)v12 + 59);
            if ( !v10 )
            {
              inited = -1073741670;
              goto LABEL_29;
            }
            memmove(v10, *(const void **)(v13 + 472), 40LL * *((unsigned int *)v12 + 120));
          }
          inited = PsInsertPermanentSiloContext(a1, KsecddSiloContextSlot, v12);
          if ( inited >= 0 )
          {
            v12 = 0;
          }
          else
          {
            v3 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
            {
              v4 = 14;
              goto LABEL_5;
            }
          }
        }
        else
        {
          v3 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
          {
            v4 = 13;
            goto LABEL_5;
          }
        }
      }
      else
      {
        v3 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
        {
          v4 = 12;
          goto LABEL_5;
        }
      }
    }
    else
    {
      v3 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      {
        v4 = 11;
        goto LABEL_5;
      }
    }
  }
  else
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
    {
      v4 = 10;
LABEL_5:
      WPP_SF_D(v3[3], v4, WPP_c96b46bc77a231c7dcb07ce7efb6a547_Traceguids, (unsigned int)inited);
    }
  }
LABEL_29:
  if ( v12 )
    ReleaseSiloKsecddLsaState(v12);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x1800233d0  mov     [rsp-8+arg_0], rbx
0x1800233d5  mov     [rsp-8+arg_18], rdi
0x1800233da  push    rbp
0x1800233db  mov     rbp, rsp
0x1800233de  sub     rsp, 30h
0x1800233e2  mov     edx, 250h
0x1800233e7  mov     [rbp+arg_8], 0
0x1800233ef  lea     rax, [rbp+arg_8]
0x1800233f3  mov     [rbp+arg_10], 0
0x1800233fb  xor     r9d, r9d
0x1800233fe  mov     [rsp+30h+BugCheckParameter4], rax
0x180023403  mov     rdi, rcx
0x180023406  lea     r8d, [rdx-50h]
0x18002340a  call    cs:__imp_PsCreateSiloContext
0x180023411  nop     dword ptr [rax+rax+00h]
0x180023416  mov     ebx, eax
0x180023418  test    eax, eax
0x18002341a  jns     short loc_18002345C
0x18002341c  mov     rcx, cs:WPP_GLOBAL_Control
0x180023423  lea     rax, WPP_GLOBAL_Control
0x18002342a  cmp     rcx, rax
0x18002342d  jz      loc_18002365F
0x180023433  mov     edx, [rcx+2Ch]
0x180023436  test    dl, 1
0x180023439  jz      loc_18002365F
0x18002343f  mov     edx, 0Ah
0x180023444  mov     rcx, [rcx+18h]
0x180023448  lea     r8, WPP_c96b46bc77a231c7dcb07ce7efb6a547_Traceguids
0x18002344f  mov     r9d, ebx
0x180023452  call    WPP_SF_D
0x180023457  jmp     loc_18002365F
0x18002345c  mov     rcx, [rbp+arg_8]; void *
0x180023460  xor     edx, edx; Val
0x180023462  mov     r8d, 250h; Size
0x180023468  call    memset
0x18002346d  mov     rcx, [rbp+arg_8]; struct _KSECDDLSASTATE *
0x180023471  call    ?KsecInitAddressValidation@@YAJPEAU_KSECDDLSASTATE@@@Z; KsecInitAddressValidation(_KSECDDLSASTATE *)
0x180023476  mov     ebx, eax
0x180023478  test    eax, eax
0x18002347a  jns     short loc_1800234A5
0x18002347c  mov     rcx, cs:WPP_GLOBAL_Control
0x180023483  lea     rax, WPP_GLOBAL_Control
0x18002348a  cmp     rcx, rax
0x18002348d  jz      loc_18002365F
0x180023493  mov     eax, [rcx+2Ch]
0x180023496  test    al, 1
0x180023498  jz      loc_18002365F
0x18002349e  mov     edx, 0Bh
0x1800234a3  jmp     short loc_180023444
0x1800234a5  mov     rax, [rbp+arg_8]
0x1800234a9  mov     qword ptr [rax+208h], 1
0x1800234b4  mov     rcx, [rbp+arg_8]
0x1800234b8  call    IoctlIpcInitSilo
0x1800234bd  mov     ebx, eax
0x1800234bf  test    eax, eax
0x1800234c1  jns     short loc_1800234EF
0x1800234c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800234ca  lea     rax, WPP_GLOBAL_Control
0x1800234d1  cmp     rcx, rax
0x1800234d4  jz      loc_18002365F
0x1800234da  mov     eax, [rcx+2Ch]
0x1800234dd  test    al, 1
0x1800234df  jz      loc_18002365F
0x1800234e5  mov     edx, 0Ch
0x1800234ea  jmp     loc_180023444
0x1800234ef  mov     rcx, [rbp+arg_8]
0x1800234f3  call    KsecPerfCountersInitSilo
0x1800234f8  mov     ebx, eax
0x1800234fa  test    eax, eax
0x1800234fc  jns     short loc_18002352A
0x1800234fe  mov     rcx, cs:WPP_GLOBAL_Control
0x180023505  lea     rax, WPP_GLOBAL_Control
0x18002350c  cmp     rcx, rax
0x18002350f  jz      loc_18002365F
0x180023515  mov     eax, [rcx+2Ch]
0x180023518  test    al, 1
0x18002351a  jz      loc_18002365F
0x180023520  mov     edx, 0Dh
0x180023525  jmp     loc_180023444
0x18002352a  mov     rcx, rdi
0x18002352d  call    cs:__imp_PsIsHostSilo
0x180023534  nop     dword ptr [rax+rax+00h]
0x180023539  test    al, al
0x18002353b  jnz     loc_180023614
0x180023541  mov     ebx, cs:?KsecddSiloContextSlot@@3KA; ulong KsecddSiloContextSlot
0x180023547  call    cs:__imp_PsGetHostSilo
0x18002354e  nop     dword ptr [rax+rax+00h]
0x180023553  lea     r8, [rbp+arg_10]
0x180023557  mov     edx, ebx
0x180023559  mov     rcx, rax
0x18002355c  call    cs:__imp_PsGetPermanentSiloContext
0x180023563  nop     dword ptr [rax+rax+00h]
0x180023568  mov     rcx, [rbp+arg_10]
0x18002356c  test    rcx, rcx
0x18002356f  jnz     short loc_1800235A1
0x180023571  call    cs:__imp_PsGetHostSilo
0x180023578  nop     dword ptr [rax+rax+00h]
0x18002357d  xor     r9d, r9d; BugCheckParameter3
0x180023580  mov     [rsp+30h+BugCheckParameter4], 0; BugCheckParameter4
0x180023589  mov     rdx, rax; BugCheckParameter1
0x18002358c  xor     r8d, r8d; BugCheckParameter2
0x18002358f  mov     ecx, 18Ah; BugCheckCode
0x180023594  call    cs:__imp_KeBugCheckEx
0x1800235a1  mov     ecx, [rcx+1E0h]
0x1800235a7  mov     r8d, 6365734Bh
0x1800235ad  mov     rax, [rbp+arg_8]
0x1800235b1  lea     rdx, [rcx+rcx*4]
0x1800235b5  mov     [rax+1E0h], ecx
0x1800235bb  mov     ecx, 40h ; '@'
0x1800235c0  shl     rdx, 3
0x1800235c4  call    cs:__imp_ExAllocatePool2
0x1800235cb  nop     dword ptr [rax+rax+00h]
0x1800235d0  mov     rcx, [rbp+arg_8]
0x1800235d4  mov     [rcx+1D8h], rax
0x1800235db  mov     rax, [rbp+arg_8]
0x1800235df  mov     rcx, [rax+1D8h]; void *
0x1800235e6  test    rcx, rcx
0x1800235e9  jnz     short loc_1800235F2
0x1800235eb  mov     ebx, 0C000009Ah
0x1800235f0  jmp     short loc_18002365F
0x1800235f2  mov     rax, [rbp+arg_8]
0x1800235f6  mov     edx, [rax+1E0h]
0x1800235fc  lea     r8, [rdx+rdx*4]
0x180023600  mov     rdx, [rbp+arg_10]
0x180023604  shl     r8, 3; Size
0x180023608  mov     rdx, [rdx+1D8h]; Src
0x18002360f  call    memmove
0x180023614  mov     r8, [rbp+arg_8]
0x180023618  mov     rcx, rdi
0x18002361b  mov     edx, cs:?KsecddSiloContextSlot@@3KA; ulong KsecddSiloContextSlot
0x180023621  call    cs:__imp_PsInsertPermanentSiloContext
0x180023628  nop     dword ptr [rax+rax+00h]
0x18002362d  mov     ebx, eax
0x18002362f  test    eax, eax
0x180023631  jns     short loc_180023657
0x180023633  mov     rcx, cs:WPP_GLOBAL_Control
0x18002363a  lea     rax, WPP_GLOBAL_Control
0x180023641  cmp     rcx, rax
0x180023644  jz      short loc_18002365F
0x180023646  mov     eax, [rcx+2Ch]
0x180023649  test    al, 1
0x18002364b  jz      short loc_18002365F
0x18002364d  mov     edx, 0Eh
0x180023652  jmp     loc_180023444
0x180023657  mov     [rbp+arg_8], 0
0x18002365f  mov     rcx, [rbp+arg_8]; struct _KSECDDLSASTATE *
0x180023663  test    rcx, rcx
0x180023666  jz      short loc_18002366D
0x180023668  call    ?ReleaseSiloKsecddLsaState@@YAXPEAU_KSECDDLSASTATE@@@Z; ReleaseSiloKsecddLsaState(_KSECDDLSASTATE *)
0x18002366d  mov     rdi, [rsp+30h+arg_18]
0x180023672  mov     eax, ebx
0x180023674  mov     rbx, [rsp+30h+arg_0]
0x180023679  add     rsp, 30h
0x18002367d  pop     rbp
0x18002367e  retn
```
