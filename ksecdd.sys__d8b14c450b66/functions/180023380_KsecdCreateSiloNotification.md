# KsecdCreateSiloNotification

- ea: `0x180023380`
- end: `0x180023630`
- name: `KsecdCreateSiloNotification`
- size: `688`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x180001ec0`
- `0x180007bd8`
- `0x18000c6d0`
- `0x180010980`
- `0x180010c80`
- `0x18001f448`
- `0x1800231f4`
- `0x180023380`

## import_xrefs

- `ntoskrnl!PsCreateSiloContext` at `0x1800233ba`
- `ntoskrnl!PsCreateSiloContext` at `0x1800233ba`
- `ntoskrnl!PsIsHostSilo` at `0x1800234dd`
- `ntoskrnl!PsIsHostSilo` at `0x1800234dd`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x18002350c`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x18002350c`
- `ntoskrnl!PsGetHostSilo` at `0x1800234f7`
- `ntoskrnl!PsGetHostSilo` at `0x180023521`
- `ntoskrnl!PsGetHostSilo` at `0x1800234f7`
- `ntoskrnl!PsGetHostSilo` at `0x180023521`
- `ntoskrnl!KeBugCheckEx` at `0x180023544`
- `ntoskrnl!KeBugCheckEx` at `0x180023544`
- `ntoskrnl!PsInsertPermanentSiloContext` at `0x1800235d1`
- `ntoskrnl!PsInsertPermanentSiloContext` at `0x1800235d1`
- `ntoskrnl!ExAllocatePool2` at `0x180023574`
- `ntoskrnl!ExAllocatePool2` at `0x180023574`

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
      inited = IoctlIpcInitSilo((__int64)v12);
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
0x180023380  mov     [rsp-8+arg_0], rbx
0x180023385  mov     [rsp-8+arg_18], rdi
0x18002338a  push    rbp
0x18002338b  mov     rbp, rsp
0x18002338e  sub     rsp, 30h
0x180023392  mov     edx, 250h
0x180023397  mov     [rbp+arg_8], 0
0x18002339f  lea     rax, [rbp+arg_8]
0x1800233a3  mov     [rbp+arg_10], 0
0x1800233ab  xor     r9d, r9d
0x1800233ae  mov     [rsp+30h+BugCheckParameter4], rax
0x1800233b3  mov     rdi, rcx
0x1800233b6  lea     r8d, [rdx-50h]
0x1800233ba  call    cs:__imp_PsCreateSiloContext
0x1800233c1  nop     dword ptr [rax+rax+00h]
0x1800233c6  mov     ebx, eax
0x1800233c8  test    eax, eax
0x1800233ca  jns     short loc_18002340C
0x1800233cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800233d3  lea     rax, WPP_GLOBAL_Control
0x1800233da  cmp     rcx, rax
0x1800233dd  jz      loc_18002360F
0x1800233e3  mov     edx, [rcx+2Ch]
0x1800233e6  test    dl, 1
0x1800233e9  jz      loc_18002360F
0x1800233ef  mov     edx, 0Ah
0x1800233f4  mov     rcx, [rcx+18h]
0x1800233f8  lea     r8, WPP_c96b46bc77a231c7dcb07ce7efb6a547_Traceguids
0x1800233ff  mov     r9d, ebx
0x180023402  call    WPP_SF_D
0x180023407  jmp     loc_18002360F
0x18002340c  mov     rcx, [rbp+arg_8]; void *
0x180023410  xor     edx, edx; Val
0x180023412  mov     r8d, 250h; Size
0x180023418  call    memset
0x18002341d  mov     rcx, [rbp+arg_8]; struct _KSECDDLSASTATE *
0x180023421  call    ?KsecInitAddressValidation@@YAJPEAU_KSECDDLSASTATE@@@Z; KsecInitAddressValidation(_KSECDDLSASTATE *)
0x180023426  mov     ebx, eax
0x180023428  test    eax, eax
0x18002342a  jns     short loc_180023455
0x18002342c  mov     rcx, cs:WPP_GLOBAL_Control
0x180023433  lea     rax, WPP_GLOBAL_Control
0x18002343a  cmp     rcx, rax
0x18002343d  jz      loc_18002360F
0x180023443  mov     eax, [rcx+2Ch]
0x180023446  test    al, 1
0x180023448  jz      loc_18002360F
0x18002344e  mov     edx, 0Bh
0x180023453  jmp     short loc_1800233F4
0x180023455  mov     rax, [rbp+arg_8]
0x180023459  mov     qword ptr [rax+208h], 1
0x180023464  mov     rcx, [rbp+arg_8]
0x180023468  call    IoctlIpcInitSilo
0x18002346d  mov     ebx, eax
0x18002346f  test    eax, eax
0x180023471  jns     short loc_18002349F
0x180023473  mov     rcx, cs:WPP_GLOBAL_Control
0x18002347a  lea     rax, WPP_GLOBAL_Control
0x180023481  cmp     rcx, rax
0x180023484  jz      loc_18002360F
0x18002348a  mov     eax, [rcx+2Ch]
0x18002348d  test    al, 1
0x18002348f  jz      loc_18002360F
0x180023495  mov     edx, 0Ch
0x18002349a  jmp     loc_1800233F4
0x18002349f  mov     rcx, [rbp+arg_8]
0x1800234a3  call    KsecPerfCountersInitSilo
0x1800234a8  mov     ebx, eax
0x1800234aa  test    eax, eax
0x1800234ac  jns     short loc_1800234DA
0x1800234ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800234b5  lea     rax, WPP_GLOBAL_Control
0x1800234bc  cmp     rcx, rax
0x1800234bf  jz      loc_18002360F
0x1800234c5  mov     eax, [rcx+2Ch]
0x1800234c8  test    al, 1
0x1800234ca  jz      loc_18002360F
0x1800234d0  mov     edx, 0Dh
0x1800234d5  jmp     loc_1800233F4
0x1800234da  mov     rcx, rdi
0x1800234dd  call    cs:__imp_PsIsHostSilo
0x1800234e4  nop     dword ptr [rax+rax+00h]
0x1800234e9  test    al, al
0x1800234eb  jnz     loc_1800235C4
0x1800234f1  mov     ebx, cs:?KsecddSiloContextSlot@@3KA; ulong KsecddSiloContextSlot
0x1800234f7  call    cs:__imp_PsGetHostSilo
0x1800234fe  nop     dword ptr [rax+rax+00h]
0x180023503  lea     r8, [rbp+arg_10]
0x180023507  mov     edx, ebx
0x180023509  mov     rcx, rax
0x18002350c  call    cs:__imp_PsGetPermanentSiloContext
0x180023513  nop     dword ptr [rax+rax+00h]
0x180023518  mov     rcx, [rbp+arg_10]
0x18002351c  test    rcx, rcx
0x18002351f  jnz     short loc_180023551
0x180023521  call    cs:__imp_PsGetHostSilo
0x180023528  nop     dword ptr [rax+rax+00h]
0x18002352d  xor     r9d, r9d; BugCheckParameter3
0x180023530  mov     [rsp+30h+BugCheckParameter4], 0; BugCheckParameter4
0x180023539  mov     rdx, rax; BugCheckParameter1
0x18002353c  xor     r8d, r8d; BugCheckParameter2
0x18002353f  mov     ecx, 18Ah; BugCheckCode
0x180023544  call    cs:__imp_KeBugCheckEx
0x180023551  mov     ecx, [rcx+1E0h]
0x180023557  mov     r8d, 6365734Bh
0x18002355d  mov     rax, [rbp+arg_8]
0x180023561  lea     rdx, [rcx+rcx*4]
0x180023565  mov     [rax+1E0h], ecx
0x18002356b  mov     ecx, 40h ; '@'
0x180023570  shl     rdx, 3
0x180023574  call    cs:__imp_ExAllocatePool2
0x18002357b  nop     dword ptr [rax+rax+00h]
0x180023580  mov     rcx, [rbp+arg_8]
0x180023584  mov     [rcx+1D8h], rax
0x18002358b  mov     rax, [rbp+arg_8]
0x18002358f  mov     rcx, [rax+1D8h]; void *
0x180023596  test    rcx, rcx
0x180023599  jnz     short loc_1800235A2
0x18002359b  mov     ebx, 0C000009Ah
0x1800235a0  jmp     short loc_18002360F
0x1800235a2  mov     rax, [rbp+arg_8]
0x1800235a6  mov     edx, [rax+1E0h]
0x1800235ac  lea     r8, [rdx+rdx*4]
0x1800235b0  mov     rdx, [rbp+arg_10]
0x1800235b4  shl     r8, 3; Size
0x1800235b8  mov     rdx, [rdx+1D8h]; Src
0x1800235bf  call    memmove
0x1800235c4  mov     r8, [rbp+arg_8]
0x1800235c8  mov     rcx, rdi
0x1800235cb  mov     edx, cs:?KsecddSiloContextSlot@@3KA; ulong KsecddSiloContextSlot
0x1800235d1  call    cs:__imp_PsInsertPermanentSiloContext
0x1800235d8  nop     dword ptr [rax+rax+00h]
0x1800235dd  mov     ebx, eax
0x1800235df  test    eax, eax
0x1800235e1  jns     short loc_180023607
0x1800235e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800235ea  lea     rax, WPP_GLOBAL_Control
0x1800235f1  cmp     rcx, rax
0x1800235f4  jz      short loc_18002360F
0x1800235f6  mov     eax, [rcx+2Ch]
0x1800235f9  test    al, 1
0x1800235fb  jz      short loc_18002360F
0x1800235fd  mov     edx, 0Eh
0x180023602  jmp     loc_1800233F4
0x180023607  mov     [rbp+arg_8], 0
0x18002360f  mov     rcx, [rbp+arg_8]; struct _KSECDDLSASTATE *
0x180023613  test    rcx, rcx
0x180023616  jz      short loc_18002361D
0x180023618  call    ?ReleaseSiloKsecddLsaState@@YAXPEAU_KSECDDLSASTATE@@@Z; ReleaseSiloKsecddLsaState(_KSECDDLSASTATE *)
0x18002361d  mov     rdi, [rsp+30h+arg_18]
0x180023622  mov     eax, ebx
0x180023624  mov     rbx, [rsp+30h+arg_0]
0x180023629  add     rsp, 30h
0x18002362d  pop     rbp
0x18002362e  retn
```
