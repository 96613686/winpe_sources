# CMsftDiscFormat2Erase::IsCurrentMediaSupported(IDiscRecorder2 *,short *)

- ea: `0x180026ff0`
- end: `0x18002715e`
- name: `?IsCurrentMediaSupported@CMsftDiscFormat2Erase@@UEAAJPEAUIDiscRecorder2@@PEAF@Z`
- size: `366`
- prototype: `__int64 __fastcall(CMsftDiscFormat2Erase *__hidden this, struct IDiscRecorder2 *, __int16 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180002fc8`
- `0x18000c2ac`
- `0x1800140f4`
- `0x180026ce0`
- `0x180026ff0`
- `0x18004a010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18002713e`
- `ole32!CoTaskMemFree` at `0x18002713e`

## pseudocode

```c
__int64 __fastcall CMsftDiscFormat2Erase::IsCurrentMediaSupported(
        CMsftDiscFormat2Erase *this,
        struct IDiscRecorder2 *a2,
        struct _GUID *a3)
{
  struct IDiscRecorder2Ex *v3; // rcx
  struct IDiscRecorder2 *v5; // r9
  signed int DiscInformation; // ebx
  struct IDiscRecorder2Vtbl *v7; // rcx
  bool v9; // di
  unsigned int v10; // [rsp+58h] [rbp+38h] BYREF
  struct IDiscRecorder2Ex *v11; // [rsp+60h] [rbp+40h] BYREF
  LPVOID pv; // [rsp+68h] [rbp+48h] BYREF

  v3 = 0;
  v11 = 0;
  pv = 0;
  v10 = 0;
  v5 = a2;
  DiscInformation = a2 == 0 ? 0x80004003 : 0;
  if ( !a3 )
    return (unsigned int)-2147467261;
  LOWORD(a3->Data1) = 0;
  if ( !a2 )
    goto LABEL_10;
  DiscInformation = ((__int64 (__fastcall *)(struct IDiscRecorder2 *, GUID *, struct IDiscRecorder2Ex **))a2->lpVtbl->QueryInterface)(
                      a2,
                      &GUID_27354132_7f64_5b0f_8f00_5d77afbe261e,
                      &v11);
  if ( DiscInformation < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 265) >= 3u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 32),
        28,
        &WPP_8ddcedaf23bb30f41053135f0cc3ba6f_Traceguids,
        (unsigned int)DiscInformation);
    }
    goto LABEL_9;
  }
  v9 = CMsftDiscFormat2Erase::CheckRecorderSupportsErase(v7, v11, 1);
  if ( v9 )
  {
    pv = 0;
    v10 = 0;
    DiscInformation = CMsftDiscFormat2Erase::GetDiscInformation(
                        v11,
                        (struct _DISC_INFORMATION **)&pv,
                        &v10,
                        (unsigned int)v5);
    if ( DiscInformation < 0 )
    {
LABEL_9:
      v3 = v11;
LABEL_10:
      if ( DiscInformation != -2147467261 )
        DiscInformation = 1;
      goto LABEL_12;
    }
    v9 = (*((_BYTE *)pv + 2) & 0x10) != 0;
    CoTaskMemFree(pv);
    pv = 0;
  }
  v3 = v11;
  LOWORD(a3->Data1) = -v9;
LABEL_12:
  if ( v3 )
  {
    ((void (__fastcall *)(struct IDiscRecorder2Ex *, struct IDiscRecorder2 *, struct _GUID *, struct IDiscRecorder2 *))v3->lpVtbl->Release)(
      v3,
      a2,
      a3,
      v5);
    v11 = 0;
  }
  if ( (DiscInformation & 0x80FF0000) == 0x80AA0000 )
    Imapi2Utility::SetErrorDescription(DiscInformation, (__int64)&CLSID_MsftDiscFormat2Erase, a3);
  return (unsigned int)DiscInformation;
}

```

## disassembly

```asm
0x180026ff0  push    rbp
0x180026ff2  push    rbx
0x180026ff3  push    rsi
0x180026ff4  push    rdi
0x180026ff5  push    r12
0x180026ff7  mov     rbp, rsp
0x180026ffa  sub     rsp, 20h
0x180026ffe  xor     ecx, ecx
0x180027000  mov     rax, rdx
0x180027003  neg     rax
0x180027006  mov     [rbp+arg_10], rcx
0x18002700a  mov     rsi, r8
0x18002700d  mov     [rbp+pv], rcx
0x180027011  sbb     ebx, ebx
0x180027013  mov     [rbp+arg_8], ecx
0x180027016  not     ebx
0x180027018  mov     r9, rdx
0x18002701b  and     ebx, 80004003h
0x180027021  test    r8, r8
0x180027024  jnz     short loc_180027030
0x180027026  mov     ebx, 80004003h
0x18002702b  jmp     loc_1800270E5
0x180027030  xor     eax, eax
0x180027032  mov     [r8], ax
0x180027036  lea     r12d, [rax+1]
0x18002703a  test    r9, r9
0x18002703d  jz      short loc_1800270A6
0x18002703f  mov     rax, [rdx]
0x180027042  lea     r8, [rbp+arg_10]
0x180027046  lea     rdx, _GUID_27354132_7f64_5b0f_8f00_5d77afbe261e
0x18002704d  mov     rcx, r9
0x180027050  mov     rax, [rax]
0x180027053  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027058  mov     ebx, eax
0x18002705a  test    eax, eax
0x18002705c  jns     loc_1800270F2
0x180027062  mov     rcx, cs:WPP_GLOBAL_Control
0x180027069  lea     rax, WPP_GLOBAL_Control
0x180027070  cmp     rcx, rax
0x180027073  jz      short loc_1800270A2
0x180027075  test    byte ptr [rcx+10Ch], 4
0x18002707c  jz      short loc_1800270A2
0x18002707e  cmp     byte ptr [rcx+109h], 3
0x180027085  jb      short loc_1800270A2
0x180027087  mov     rcx, [rcx+100h]
0x18002708e  lea     edx, [r12+1Bh]
0x180027093  mov     r9d, ebx
0x180027096  lea     r8, WPP_8ddcedaf23bb30f41053135f0cc3ba6f_Traceguids
0x18002709d  call    WPP_SF_d
0x1800270a2  mov     rcx, [rbp+arg_10]
0x1800270a6  cmp     ebx, 80004003h
0x1800270ac  cmovnz  ebx, r12d
0x1800270b0  test    rcx, rcx
0x1800270b3  jz      short loc_1800270C9
0x1800270b5  mov     rax, [rcx]
0x1800270b8  mov     rax, [rax+10h]
0x1800270bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800270c1  mov     [rbp+arg_10], 0
0x1800270c9  mov     eax, ebx
0x1800270cb  and     eax, 80FF0000h
0x1800270d0  cmp     eax, 80AA0000h
0x1800270d5  jnz     short loc_1800270E5
0x1800270d7  lea     rdx, CLSID_MsftDiscFormat2Erase; int
0x1800270de  mov     ecx, ebx; dwMessageId
0x1800270e0  call    ?SetErrorDescription@Imapi2Utility@@YAXJAEBU_GUID@@@Z; Imapi2Utility::SetErrorDescription(long,_GUID const &)
0x1800270e5  mov     eax, ebx
0x1800270e7  add     rsp, 20h
0x1800270eb  pop     r12
0x1800270ed  pop     rdi
0x1800270ee  pop     rsi
0x1800270ef  pop     rbx
0x1800270f0  pop     rbp
0x1800270f1  retn
0x1800270f2  mov     rdx, [rbp+arg_10]; struct IDiscRecorder2Ex *
0x1800270f6  mov     r8b, r12b; unsigned __int8
0x1800270f9  call    ?CheckRecorderSupportsErase@CMsftDiscFormat2Erase@@AEAAEPEAUIDiscRecorder2Ex@@E@Z; CMsftDiscFormat2Erase::CheckRecorderSupportsErase(IDiscRecorder2Ex *,uchar)
0x1800270fe  mov     dil, al
0x180027101  test    al, al
0x180027103  jz      short loc_18002714C
0x180027105  mov     rcx, [rbp+arg_10]; struct IDiscRecorder2Ex *
0x180027109  lea     r8, [rbp+arg_8]; unsigned int *
0x18002710d  lea     rdx, [rbp+pv]; struct _DISC_INFORMATION **
0x180027111  mov     [rbp+pv], 0
0x180027119  mov     [rbp+arg_8], 0
0x180027120  call    ?GetDiscInformation@CMsftDiscFormat2Erase@@CAJPEAUIDiscRecorder2Ex@@PEAPEAU_DISC_INFORMATION@@PEAKK@Z; CMsftDiscFormat2Erase::GetDiscInformation(IDiscRecorder2Ex *,_DISC_INFORMATION * *,ulong *,ulong)
0x180027125  mov     ebx, eax
0x180027127  test    eax, eax
0x180027129  js      loc_1800270A2
0x18002712f  mov     rcx, [rbp+pv]; pv
0x180027133  mov     dil, [rcx+2]
0x180027137  shr     dil, 4
0x18002713b  and     dil, r12b
0x18002713e  call    cs:__imp_CoTaskMemFree
0x180027144  mov     [rbp+pv], 0
0x18002714c  mov     rcx, [rbp+arg_10]
0x180027150  neg     dil
0x180027153  sbb     ax, ax
0x180027156  mov     [rsi], ax
0x180027159  jmp     loc_1800270B0
```
