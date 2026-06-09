# Dot3AcmSetUserDataByGuid(_GUID const *,void *,ulong,uchar *)

- ea: `0x180021b40`
- end: `0x180021d3a`
- name: `?Dot3AcmSetUserDataByGuid@@YAKPEBU_GUID@@PEAXKPEAE@Z`
- size: `506`
- prototype: `__int64 __fastcall(const struct _GUID *, HANDLE TokenHandle, DWORD, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180016390`

## callees

- `0x1800025f0`
- `0x18000a9c0`
- `0x18000c230`
- `0x18000ce28`
- `0x1800106ec`
- `0x180019a5c`
- `0x180021b40`
- `0x18002226c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021cbb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021cbb`
- `MobileNetworking!HtDereferenceHandleWithTag` at `0x180021ce9`
- `MobileNetworking!HtDereferenceHandleWithTag` at `0x180021ce9`
- `MobileNetworking!HtReferenceHandleWithTag` at `0x180021c5a`
- `MobileNetworking!HtReferenceHandleWithTag` at `0x180021c5a`

## pseudocode

```c
__int64 __fastcall Dot3AcmSetUserDataByGuid(const struct _GUID *a1, HANDLE TokenHandle, DWORD a3, unsigned __int8 *a4)
{
  void *v4; // rdi
  struct _LIST_ENTRY *v9; // rcx
  unsigned int InterfaceProfileGuid; // ebx
  unsigned int InterfaceContextHandle; // eax
  struct _LAN_INTERFACE_CONTEXT *v12; // rcx
  unsigned int v13; // eax
  struct _LAN_INTERFACE_CONTEXT *v15; // [rsp+40h] [rbp-38h] BYREF
  void *v16; // [rsp+48h] [rbp-30h] BYREF
  struct _GUID v17; // [rsp+50h] [rbp-28h] BYREF

  v4 = 0;
  v16 = 0;
  v15 = 0;
  v17 = 0;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 78, WPP_81374dd11c13362d0a381c62b18e62ba_Traceguids);
    v9 = WPP_GLOBAL_Control;
  }
  if ( a1 )
  {
    InterfaceContextHandle = WimGetInterfaceContextHandle(a1, &v16);
    InterfaceProfileGuid = InterfaceContextHandle;
    if ( InterfaceContextHandle )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control[1].Blink)
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control[1].Flink,
          79,
          WPP_81374dd11c13362d0a381c62b18e62ba_Traceguids,
          InterfaceContextHandle);
        v9 = WPP_GLOBAL_Control;
        v4 = v16;
      }
      else
      {
        v4 = v16;
      }
    }
    else
    {
      v4 = v16;
      if ( v16 )
      {
        InterfaceProfileGuid = HtReferenceHandleWithTag(g_hHandleTable, v16, 1229870150, 0, 1, &v15);
        if ( !InterfaceProfileGuid )
        {
          InterfaceProfileGuid = IntfLockInterface(v15);
          if ( !InterfaceProfileGuid )
          {
            InterfaceProfileGuid = GetInterfaceProfileGuid(v15, &v17);
            if ( !InterfaceProfileGuid )
            {
              v13 = PmSaveUserData(TokenHandle, (struct _GUID *)((char *)v12 + 8), &v17, L"Wired", a3, a4, 1);
              v12 = v15;
              InterfaceProfileGuid = v13;
            }
            LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v12 + 128));
          }
        }
      }
      else
      {
        InterfaceProfileGuid = 87;
      }
      v9 = WPP_GLOBAL_Control;
    }
  }
  else
  {
    InterfaceProfileGuid = 87;
  }
  if ( v15 )
  {
    HtDereferenceHandleWithTag(g_hHandleTable, v4, 0, 1);
    v9 = WPP_GLOBAL_Control;
  }
  if ( v9 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && BYTE1(v9[1].Blink) >= 4u && (BYTE4(v9[1].Blink) & 1) != 0 )
    WPP_SF_d(v9[1].Flink, 80, WPP_81374dd11c13362d0a381c62b18e62ba_Traceguids, InterfaceProfileGuid);
  return InterfaceProfileGuid;
}

```

## disassembly

```asm
0x180021b40  push    rbp
0x180021b42  push    rbx
0x180021b43  push    rsi
0x180021b44  push    rdi
0x180021b45  push    r14
0x180021b47  push    r15
0x180021b49  mov     rbp, rsp
0x180021b4c  sub     rsp, 78h
0x180021b50  mov     rax, cs:__security_cookie
0x180021b57  xor     rax, rsp
0x180021b5a  mov     [rbp+var_18], rax
0x180021b5e  xor     edi, edi
0x180021b60  xorps   xmm0, xmm0
0x180021b63  mov     [rbp+var_30], rdi
0x180021b67  mov     r15, r9
0x180021b6a  mov     [rbp+var_38], rdi
0x180021b6e  mov     r14d, r8d
0x180021b71  movups  xmmword ptr [rbp+var_28.Data1], xmm0
0x180021b75  mov     rsi, rdx
0x180021b78  mov     rbx, rcx
0x180021b7b  mov     rcx, cs:WPP_GLOBAL_Control
0x180021b82  lea     rax, WPP_GLOBAL_Control
0x180021b89  cmp     rcx, rax
0x180021b8c  jz      short loc_180021BB4
0x180021b8e  cmp     byte ptr [rcx+19h], 4
0x180021b92  jb      short loc_180021BB4
0x180021b94  test    byte ptr [rcx+1Ch], 1
0x180021b98  jz      short loc_180021BB4
0x180021b9a  mov     rcx, [rcx+10h]
0x180021b9e  lea     edx, [rdi+4Eh]
0x180021ba1  lea     r8, WPP_81374dd11c13362d0a381c62b18e62ba_Traceguids
0x180021ba8  call    WPP_SF_
0x180021bad  mov     rcx, cs:WPP_GLOBAL_Control
0x180021bb4  test    rbx, rbx
0x180021bb7  jnz     short loc_180021BC3
0x180021bb9  mov     ebx, 57h ; 'W'
0x180021bbe  jmp     loc_180021CC8
0x180021bc3  lea     rdx, [rbp+var_30]; void **
0x180021bc7  mov     rcx, rbx; struct _GUID *
0x180021bca  call    ?WimGetInterfaceContextHandle@@YAKPEBU_GUID@@PEAPEAX@Z; WimGetInterfaceContextHandle(_GUID const *,void * *)
0x180021bcf  mov     ebx, eax
0x180021bd1  test    eax, eax
0x180021bd3  jz      short loc_180021C25
0x180021bd5  mov     rcx, cs:WPP_GLOBAL_Control
0x180021bdc  lea     rsi, WPP_GLOBAL_Control
0x180021be3  cmp     rcx, rsi
0x180021be6  jz      short loc_180021C1C
0x180021be8  cmp     byte ptr [rcx+19h], 1
0x180021bec  jb      short loc_180021C1C
0x180021bee  test    byte ptr [rcx+1Ch], 1
0x180021bf2  jz      short loc_180021C1C
0x180021bf4  mov     rcx, [rcx+10h]
0x180021bf8  lea     r8, WPP_81374dd11c13362d0a381c62b18e62ba_Traceguids
0x180021bff  mov     edx, 4Fh ; 'O'
0x180021c04  mov     r9d, eax
0x180021c07  call    WPP_SF_d
0x180021c0c  mov     rcx, cs:WPP_GLOBAL_Control
0x180021c13  mov     rdi, [rbp+var_30]
0x180021c17  jmp     loc_180021CCF
0x180021c1c  mov     rdi, [rbp+var_30]
0x180021c20  jmp     loc_180021CCF
0x180021c25  mov     rdi, [rbp+var_30]
0x180021c29  test    rdi, rdi
0x180021c2c  jnz     short loc_180021C36
0x180021c2e  lea     ebx, [rdi+57h]
0x180021c31  jmp     loc_180021CC1
0x180021c36  mov     rcx, cs:?g_hHandleTable@@3PEAXEA; void * g_hHandleTable
0x180021c3d  lea     rax, [rbp+var_38]
0x180021c41  mov     [rsp+78h+var_50], rax
0x180021c46  xor     r9d, r9d
0x180021c49  mov     r8d, 494E5446h
0x180021c4f  mov     [rsp+78h+var_58], 1
0x180021c57  mov     rdx, rdi
0x180021c5a  call    cs:__imp_HtReferenceHandleWithTag
0x180021c60  mov     ebx, eax
0x180021c62  test    eax, eax
0x180021c64  jnz     short loc_180021CC1
0x180021c66  mov     rcx, [rbp+var_38]; struct _LAN_INTERFACE_CONTEXT *
0x180021c6a  call    ?IntfLockInterface@@YAKPEAU_LAN_INTERFACE_CONTEXT@@@Z; IntfLockInterface(_LAN_INTERFACE_CONTEXT *)
0x180021c6f  mov     ebx, eax
0x180021c71  test    eax, eax
0x180021c73  jnz     short loc_180021CC1
0x180021c75  mov     rcx, [rbp+var_38]; struct _LAN_INTERFACE_CONTEXT *
0x180021c79  lea     rdx, [rbp+var_28]; struct _GUID *
0x180021c7d  call    ?GetInterfaceProfileGuid@@YAKPEAU_LAN_INTERFACE_CONTEXT@@PEAU_GUID@@@Z; GetInterfaceProfileGuid(_LAN_INTERFACE_CONTEXT *,_GUID *)
0x180021c82  mov     ebx, eax
0x180021c84  test    eax, eax
0x180021c86  jnz     short loc_180021CB7
0x180021c88  lea     rdx, [rcx+8]; struct _GUID *
0x180021c8c  mov     [rsp+78h+var_48], 1; int
0x180021c94  mov     [rsp+78h+var_50], r15; unsigned __int8 *
0x180021c99  lea     r9, aWired; "Wired"
0x180021ca0  mov     rcx, rsi; TokenHandle
0x180021ca3  mov     [rsp+78h+var_58], r14d; unsigned int
0x180021ca8  lea     r8, [rbp+var_28]; struct _GUID *
0x180021cac  call    ?PmSaveUserData@@YAKPEAXPEBU_GUID@@1PEAGKPEAEH@Z; PmSaveUserData(void *,_GUID const *,_GUID const *,ushort *,ulong,uchar *,int)
0x180021cb1  mov     rcx, [rbp+var_38]
0x180021cb5  mov     ebx, eax
0x180021cb7  sub     rcx, 0FFFFFFFFFFFFFF80h; lpCriticalSection
0x180021cbb  call    cs:__imp_LeaveCriticalSection
0x180021cc1  mov     rcx, cs:WPP_GLOBAL_Control
0x180021cc8  lea     rsi, WPP_GLOBAL_Control
0x180021ccf  cmp     [rbp+var_38], 0
0x180021cd4  jz      short loc_180021CF6
0x180021cd6  mov     rcx, cs:?g_hHandleTable@@3PEAXEA; void * g_hHandleTable
0x180021cdd  mov     r9d, 1
0x180021ce3  xor     r8d, r8d
0x180021ce6  mov     rdx, rdi
0x180021ce9  call    cs:__imp_HtDereferenceHandleWithTag
0x180021cef  mov     rcx, cs:WPP_GLOBAL_Control
0x180021cf6  cmp     rcx, rsi
0x180021cf9  jz      short loc_180021D1F
0x180021cfb  cmp     byte ptr [rcx+19h], 4
0x180021cff  jb      short loc_180021D1F
0x180021d01  test    byte ptr [rcx+1Ch], 1
0x180021d05  jz      short loc_180021D1F
0x180021d07  mov     rcx, [rcx+10h]
0x180021d0b  lea     r8, WPP_81374dd11c13362d0a381c62b18e62ba_Traceguids
0x180021d12  mov     edx, 50h ; 'P'
0x180021d17  mov     r9d, ebx
0x180021d1a  call    WPP_SF_d
0x180021d1f  mov     eax, ebx
0x180021d21  mov     rcx, [rbp+var_18]
0x180021d25  xor     rcx, rsp; StackCookie
0x180021d28  call    __security_check_cookie
0x180021d2d  add     rsp, 78h
0x180021d31  pop     r15
0x180021d33  pop     r14
0x180021d35  pop     rdi
0x180021d36  pop     rsi
0x180021d37  pop     rbx
0x180021d38  pop     rbp
0x180021d39  retn
```
