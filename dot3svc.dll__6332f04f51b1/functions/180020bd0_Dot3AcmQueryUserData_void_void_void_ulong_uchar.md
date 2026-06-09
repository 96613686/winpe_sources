# Dot3AcmQueryUserData(void *,void *,void *,ulong *,uchar * *)

- ea: `0x180020bd0`
- end: `0x180020d9b`
- name: `?Dot3AcmQueryUserData@@YAKPEAX00PEAKPEAPEAE@Z`
- size: `459`
- prototype: `__int64 __fastcall(void *, void *, HANDLE TokenHandle, unsigned __int16 *, unsigned __int8 **)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x18000a9c0`
- `0x18000c230`
- `0x18001953c`
- `0x180019a5c`
- `0x1800206f8`
- `0x180020844`
- `0x180020bd0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020d2e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020d2e`
- `MobileNetworking!HtDereferenceHandleWithTag` at `0x180020d56`
- `MobileNetworking!HtDereferenceHandleWithTag` at `0x180020d56`
- `MobileNetworking!HtReferenceHandleWithTag` at `0x180020c5f`
- `MobileNetworking!HtReferenceHandleWithTag` at `0x180020c5f`

## pseudocode

```c
__int64 __fastcall Dot3AcmQueryUserData(
        void *a1,
        void *a2,
        HANDLE TokenHandle,
        unsigned __int16 *a4,
        unsigned __int8 **a5)
{
  struct _LIST_ENTRY *v9; // rcx
  unsigned int v10; // ebx
  unsigned int MachineUserData; // eax
  struct _LIST_ENTRY *v12; // rcx
  __int64 v13; // rdx
  struct _LAN_INTERFACE_CONTEXT *v15; // [rsp+70h] [rbp+8h] BYREF

  v15 = 0;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 66, WPP_81374dd11c13362d0a381c62b18e62ba_Traceguids);
    v9 = WPP_GLOBAL_Control;
  }
  if ( !a1 )
  {
    v10 = 87;
    goto LABEL_24;
  }
  v10 = HtReferenceHandleWithTag(g_hHandleTable, a1, 1229870150, 0, 1, &v15);
  if ( !v10 )
  {
    v10 = IntfLockInterface(v15);
    if ( !v10 )
    {
      if ( (unsigned int)IntfIsValidMsmState(a1, a2) )
      {
        if ( *((_DWORD *)v15 + 76) == 2 )
        {
          MachineUserData = Dot3AcmQueryMachineUserData(TokenHandle, a4, a5);
          v10 = MachineUserData;
          if ( !MachineUserData )
            goto LABEL_22;
          v12 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            || !BYTE1(WPP_GLOBAL_Control[1].Blink)
            || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
          {
            goto LABEL_22;
          }
          v13 = 67;
        }
        else
        {
          MachineUserData = Dot3AcmQueryInterfaceUserData(v15, TokenHandle, (unsigned int *)a4, a5);
          v10 = MachineUserData;
          if ( !MachineUserData )
            goto LABEL_22;
          v12 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            || !BYTE1(WPP_GLOBAL_Control[1].Blink)
            || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
          {
            goto LABEL_22;
          }
          v13 = 68;
        }
        WPP_SF_d(v12[1].Flink, v13, WPP_81374dd11c13362d0a381c62b18e62ba_Traceguids, MachineUserData);
      }
LABEL_22:
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v15 + 128));
    }
  }
  v9 = WPP_GLOBAL_Control;
LABEL_24:
  if ( v15 )
  {
    HtDereferenceHandleWithTag(g_hHandleTable, a1, 0, 1);
    v9 = WPP_GLOBAL_Control;
  }
  if ( v9 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && BYTE1(v9[1].Blink) >= 4u && (BYTE4(v9[1].Blink) & 1) != 0 )
    WPP_SF_d(v9[1].Flink, 69, WPP_81374dd11c13362d0a381c62b18e62ba_Traceguids, v10);
  return v10;
}

```

## disassembly

```asm
0x180020bd0  push    rbx
0x180020bd2  push    rbp
0x180020bd3  push    rsi
0x180020bd4  push    rdi
0x180020bd5  push    r12
0x180020bd7  push    r14
0x180020bd9  sub     rsp, 38h
0x180020bdd  mov     rsi, r9
0x180020be0  mov     [rsp+68h+arg_0], 0
0x180020be9  mov     rbp, r8
0x180020bec  mov     r14, rdx
0x180020bef  mov     rdi, rcx
0x180020bf2  mov     rcx, cs:WPP_GLOBAL_Control
0x180020bf9  lea     r12, WPP_GLOBAL_Control
0x180020c00  cmp     rcx, r12
0x180020c03  jz      short loc_180020C2D
0x180020c05  cmp     byte ptr [rcx+19h], 4
0x180020c09  jb      short loc_180020C2D
0x180020c0b  test    byte ptr [rcx+1Ch], 1
0x180020c0f  jz      short loc_180020C2D
0x180020c11  mov     rcx, [rcx+10h]
0x180020c15  lea     r8, WPP_81374dd11c13362d0a381c62b18e62ba_Traceguids
0x180020c1c  mov     edx, 42h ; 'B'
0x180020c21  call    WPP_SF_
0x180020c26  mov     rcx, cs:WPP_GLOBAL_Control
0x180020c2d  test    rdi, rdi
0x180020c30  jnz     short loc_180020C3A
0x180020c32  lea     ebx, [rdi+57h]
0x180020c35  jmp     loc_180020D3B
0x180020c3a  mov     rcx, cs:?g_hHandleTable@@3PEAXEA; void * g_hHandleTable
0x180020c41  lea     rax, [rsp+68h+arg_0]
0x180020c46  mov     [rsp+68h+var_40], rax
0x180020c4b  xor     r9d, r9d
0x180020c4e  mov     r8d, 494E5446h
0x180020c54  mov     [rsp+68h+var_48], 1
0x180020c5c  mov     rdx, rdi
0x180020c5f  call    cs:__imp_HtReferenceHandleWithTag
0x180020c65  mov     ebx, eax
0x180020c67  test    eax, eax
0x180020c69  jnz     loc_180020D34
0x180020c6f  mov     rcx, [rsp+68h+arg_0]; struct _LAN_INTERFACE_CONTEXT *
0x180020c74  call    ?IntfLockInterface@@YAKPEAU_LAN_INTERFACE_CONTEXT@@@Z; IntfLockInterface(_LAN_INTERFACE_CONTEXT *)
0x180020c79  mov     ebx, eax
0x180020c7b  test    eax, eax
0x180020c7d  jnz     loc_180020D34
0x180020c83  mov     rdx, r14; void *
0x180020c86  mov     rcx, rdi; void *
0x180020c89  call    ?IntfIsValidMsmState@@YAHPEAX0@Z; IntfIsValidMsmState(void *,void *)
0x180020c8e  test    eax, eax
0x180020c90  jz      loc_180020D25
0x180020c96  mov     rcx, [rsp+68h+arg_0]; struct _LAN_INTERFACE_CONTEXT *
0x180020c9b  cmp     dword ptr [rcx+130h], 2
0x180020ca2  jnz     short loc_180020CDC
0x180020ca4  mov     r8, [rsp+68h+arg_20]; unsigned __int8 **
0x180020cac  mov     rdx, rsi; unsigned int *
0x180020caf  mov     rcx, rbp; TokenHandle
0x180020cb2  call    ?Dot3AcmQueryMachineUserData@@YAKPEAXPEAKPEAPEAE@Z; Dot3AcmQueryMachineUserData(void *,ulong *,uchar * *)
0x180020cb7  mov     ebx, eax
0x180020cb9  test    eax, eax
0x180020cbb  jz      short loc_180020D25
0x180020cbd  mov     rcx, cs:WPP_GLOBAL_Control
0x180020cc4  cmp     rcx, r12
0x180020cc7  jz      short loc_180020D25
0x180020cc9  cmp     byte ptr [rcx+19h], 1
0x180020ccd  jb      short loc_180020D25
0x180020ccf  test    byte ptr [rcx+1Ch], 1
0x180020cd3  jz      short loc_180020D25
0x180020cd5  mov     edx, 43h ; 'C'
0x180020cda  jmp     short loc_180020D12
0x180020cdc  mov     r9, [rsp+68h+arg_20]; unsigned __int8 **
0x180020ce4  mov     r8, rsi; unsigned int *
0x180020ce7  mov     rdx, rbp; TokenHandle
0x180020cea  call    ?Dot3AcmQueryInterfaceUserData@@YAKPEAU_LAN_INTERFACE_CONTEXT@@PEAXPEAKPEAPEAE@Z; Dot3AcmQueryInterfaceUserData(_LAN_INTERFACE_CONTEXT *,void *,ulong *,uchar * *)
0x180020cef  mov     ebx, eax
0x180020cf1  test    eax, eax
0x180020cf3  jz      short loc_180020D25
0x180020cf5  mov     rcx, cs:WPP_GLOBAL_Control
0x180020cfc  cmp     rcx, r12
0x180020cff  jz      short loc_180020D25
0x180020d01  cmp     byte ptr [rcx+19h], 1
0x180020d05  jb      short loc_180020D25
0x180020d07  test    byte ptr [rcx+1Ch], 1
0x180020d0b  jz      short loc_180020D25
0x180020d0d  mov     edx, 44h ; 'D'
0x180020d12  mov     rcx, [rcx+10h]
0x180020d16  lea     r8, WPP_81374dd11c13362d0a381c62b18e62ba_Traceguids
0x180020d1d  mov     r9d, eax
0x180020d20  call    WPP_SF_d
0x180020d25  mov     rcx, [rsp+68h+arg_0]
0x180020d2a  sub     rcx, 0FFFFFFFFFFFFFF80h; lpCriticalSection
0x180020d2e  call    cs:__imp_LeaveCriticalSection
0x180020d34  mov     rcx, cs:WPP_GLOBAL_Control
0x180020d3b  cmp     [rsp+68h+arg_0], 0
0x180020d41  jz      short loc_180020D63
0x180020d43  mov     rcx, cs:?g_hHandleTable@@3PEAXEA; void * g_hHandleTable
0x180020d4a  mov     r9d, 1
0x180020d50  xor     r8d, r8d
0x180020d53  mov     rdx, rdi
0x180020d56  call    cs:__imp_HtDereferenceHandleWithTag
0x180020d5c  mov     rcx, cs:WPP_GLOBAL_Control
0x180020d63  cmp     rcx, r12
0x180020d66  jz      short loc_180020D8C
0x180020d68  cmp     byte ptr [rcx+19h], 4
0x180020d6c  jb      short loc_180020D8C
0x180020d6e  test    byte ptr [rcx+1Ch], 1
0x180020d72  jz      short loc_180020D8C
0x180020d74  mov     rcx, [rcx+10h]
0x180020d78  lea     r8, WPP_81374dd11c13362d0a381c62b18e62ba_Traceguids
0x180020d7f  mov     edx, 45h ; 'E'
0x180020d84  mov     r9d, ebx
0x180020d87  call    WPP_SF_d
0x180020d8c  mov     eax, ebx
0x180020d8e  add     rsp, 38h
0x180020d92  pop     r14
0x180020d94  pop     r12
0x180020d96  pop     rdi
0x180020d97  pop     rsi
0x180020d98  pop     rbp
0x180020d99  pop     rbx
0x180020d9a  retn
```
