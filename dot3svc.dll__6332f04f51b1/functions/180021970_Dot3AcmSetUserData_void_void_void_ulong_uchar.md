# Dot3AcmSetUserData(void *,void *,void *,ulong,uchar *)

- ea: `0x180021970`
- end: `0x180021b3a`
- name: `?Dot3AcmSetUserData@@YAKPEAX00KPEAE@Z`
- size: `458`
- prototype: `__int64 __fastcall(void *, void *, HANDLE TokenHandle, DWORD, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x18000a9c0`
- `0x18000c230`
- `0x18001953c`
- `0x180019a5c`
- `0x180021270`
- `0x1800213c4`
- `0x180021970`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021acd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021acd`
- `MobileNetworking!HtDereferenceHandleWithTag` at `0x180021af5`
- `MobileNetworking!HtDereferenceHandleWithTag` at `0x180021af5`
- `MobileNetworking!HtReferenceHandleWithTag` at `0x1800219ff`
- `MobileNetworking!HtReferenceHandleWithTag` at `0x1800219ff`

## pseudocode

```c
__int64 __fastcall Dot3AcmSetUserData(void *a1, void *a2, HANDLE TokenHandle, DWORD a4, unsigned __int8 *a5)
{
  struct _LIST_ENTRY *v9; // rcx
  unsigned int v10; // ebx
  unsigned int v11; // eax
  struct _LIST_ENTRY *v12; // rcx
  __int64 v13; // rdx
  struct _LAN_INTERFACE_CONTEXT *v15; // [rsp+70h] [rbp+8h] BYREF

  v15 = 0;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 85, WPP_81374dd11c13362d0a381c62b18e62ba_Traceguids);
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
          v11 = Dot3AcmSetMachineUserData(TokenHandle, (const unsigned __int16 *)a4, a5);
          v10 = v11;
          if ( !v11 )
            goto LABEL_22;
          v12 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            || !BYTE1(WPP_GLOBAL_Control[1].Blink)
            || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
          {
            goto LABEL_22;
          }
          v13 = 86;
        }
        else
        {
          v11 = Dot3AcmSetInterfaceUserData(v15, TokenHandle, a4, a5);
          v10 = v11;
          if ( !v11 )
            goto LABEL_22;
          v12 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            || !BYTE1(WPP_GLOBAL_Control[1].Blink)
            || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
          {
            goto LABEL_22;
          }
          v13 = 87;
        }
        WPP_SF_d(v12[1].Flink, v13, WPP_81374dd11c13362d0a381c62b18e62ba_Traceguids, v11);
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
    WPP_SF_d(v9[1].Flink, 88, WPP_81374dd11c13362d0a381c62b18e62ba_Traceguids, v10);
  return v10;
}

```

## disassembly

```asm
0x180021970  push    rbx
0x180021972  push    rbp
0x180021973  push    rsi
0x180021974  push    rdi
0x180021975  push    r12
0x180021977  push    r14
0x180021979  sub     rsp, 38h
0x18002197d  mov     esi, r9d
0x180021980  mov     [rsp+68h+arg_0], 0
0x180021989  mov     rbp, r8
0x18002198c  mov     r14, rdx
0x18002198f  mov     rdi, rcx
0x180021992  mov     rcx, cs:WPP_GLOBAL_Control
0x180021999  lea     r12, WPP_GLOBAL_Control
0x1800219a0  cmp     rcx, r12
0x1800219a3  jz      short loc_1800219CD
0x1800219a5  cmp     byte ptr [rcx+19h], 4
0x1800219a9  jb      short loc_1800219CD
0x1800219ab  test    byte ptr [rcx+1Ch], 1
0x1800219af  jz      short loc_1800219CD
0x1800219b1  mov     rcx, [rcx+10h]
0x1800219b5  lea     r8, WPP_81374dd11c13362d0a381c62b18e62ba_Traceguids
0x1800219bc  mov     edx, 55h ; 'U'
0x1800219c1  call    WPP_SF_
0x1800219c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800219cd  test    rdi, rdi
0x1800219d0  jnz     short loc_1800219DA
0x1800219d2  lea     ebx, [rdi+57h]
0x1800219d5  jmp     loc_180021ADA
0x1800219da  mov     rcx, cs:?g_hHandleTable@@3PEAXEA; void * g_hHandleTable
0x1800219e1  lea     rax, [rsp+68h+arg_0]
0x1800219e6  mov     [rsp+68h+var_40], rax
0x1800219eb  xor     r9d, r9d
0x1800219ee  mov     r8d, 494E5446h
0x1800219f4  mov     [rsp+68h+var_48], 1
0x1800219fc  mov     rdx, rdi
0x1800219ff  call    cs:__imp_HtReferenceHandleWithTag
0x180021a05  mov     ebx, eax
0x180021a07  test    eax, eax
0x180021a09  jnz     loc_180021AD3
0x180021a0f  mov     rcx, [rsp+68h+arg_0]; struct _LAN_INTERFACE_CONTEXT *
0x180021a14  call    ?IntfLockInterface@@YAKPEAU_LAN_INTERFACE_CONTEXT@@@Z; IntfLockInterface(_LAN_INTERFACE_CONTEXT *)
0x180021a19  mov     ebx, eax
0x180021a1b  test    eax, eax
0x180021a1d  jnz     loc_180021AD3
0x180021a23  mov     rdx, r14; void *
0x180021a26  mov     rcx, rdi; void *
0x180021a29  call    ?IntfIsValidMsmState@@YAHPEAX0@Z; IntfIsValidMsmState(void *,void *)
0x180021a2e  test    eax, eax
0x180021a30  jz      loc_180021AC4
0x180021a36  mov     rcx, [rsp+68h+arg_0]; struct _LAN_INTERFACE_CONTEXT *
0x180021a3b  cmp     dword ptr [rcx+130h], 2
0x180021a42  jnz     short loc_180021A7B
0x180021a44  mov     r8, [rsp+68h+arg_20]; unsigned __int8 *
0x180021a4c  mov     edx, esi; unsigned int
0x180021a4e  mov     rcx, rbp; TokenHandle
0x180021a51  call    ?Dot3AcmSetMachineUserData@@YAKPEAXKPEAE@Z; Dot3AcmSetMachineUserData(void *,ulong,uchar *)
0x180021a56  mov     ebx, eax
0x180021a58  test    eax, eax
0x180021a5a  jz      short loc_180021AC4
0x180021a5c  mov     rcx, cs:WPP_GLOBAL_Control
0x180021a63  cmp     rcx, r12
0x180021a66  jz      short loc_180021AC4
0x180021a68  cmp     byte ptr [rcx+19h], 1
0x180021a6c  jb      short loc_180021AC4
0x180021a6e  test    byte ptr [rcx+1Ch], 1
0x180021a72  jz      short loc_180021AC4
0x180021a74  mov     edx, 56h ; 'V'
0x180021a79  jmp     short loc_180021AB1
0x180021a7b  mov     r9, [rsp+68h+arg_20]; unsigned __int8 *
0x180021a83  mov     r8d, esi; unsigned int
0x180021a86  mov     rdx, rbp; TokenHandle
0x180021a89  call    ?Dot3AcmSetInterfaceUserData@@YAKPEAU_LAN_INTERFACE_CONTEXT@@PEAXKPEAE@Z; Dot3AcmSetInterfaceUserData(_LAN_INTERFACE_CONTEXT *,void *,ulong,uchar *)
0x180021a8e  mov     ebx, eax
0x180021a90  test    eax, eax
0x180021a92  jz      short loc_180021AC4
0x180021a94  mov     rcx, cs:WPP_GLOBAL_Control
0x180021a9b  cmp     rcx, r12
0x180021a9e  jz      short loc_180021AC4
0x180021aa0  cmp     byte ptr [rcx+19h], 1
0x180021aa4  jb      short loc_180021AC4
0x180021aa6  test    byte ptr [rcx+1Ch], 1
0x180021aaa  jz      short loc_180021AC4
0x180021aac  mov     edx, 57h ; 'W'
0x180021ab1  mov     rcx, [rcx+10h]
0x180021ab5  lea     r8, WPP_81374dd11c13362d0a381c62b18e62ba_Traceguids
0x180021abc  mov     r9d, eax
0x180021abf  call    WPP_SF_d
0x180021ac4  mov     rcx, [rsp+68h+arg_0]
0x180021ac9  sub     rcx, 0FFFFFFFFFFFFFF80h; lpCriticalSection
0x180021acd  call    cs:__imp_LeaveCriticalSection
0x180021ad3  mov     rcx, cs:WPP_GLOBAL_Control
0x180021ada  cmp     [rsp+68h+arg_0], 0
0x180021ae0  jz      short loc_180021B02
0x180021ae2  mov     rcx, cs:?g_hHandleTable@@3PEAXEA; void * g_hHandleTable
0x180021ae9  mov     r9d, 1
0x180021aef  xor     r8d, r8d
0x180021af2  mov     rdx, rdi
0x180021af5  call    cs:__imp_HtDereferenceHandleWithTag
0x180021afb  mov     rcx, cs:WPP_GLOBAL_Control
0x180021b02  cmp     rcx, r12
0x180021b05  jz      short loc_180021B2B
0x180021b07  cmp     byte ptr [rcx+19h], 4
0x180021b0b  jb      short loc_180021B2B
0x180021b0d  test    byte ptr [rcx+1Ch], 1
0x180021b11  jz      short loc_180021B2B
0x180021b13  mov     rcx, [rcx+10h]
0x180021b17  lea     r8, WPP_81374dd11c13362d0a381c62b18e62ba_Traceguids
0x180021b1e  mov     edx, 58h ; 'X'
0x180021b23  mov     r9d, ebx
0x180021b26  call    WPP_SF_d
0x180021b2b  mov     eax, ebx
0x180021b2d  add     rsp, 38h
0x180021b31  pop     r14
0x180021b33  pop     r12
0x180021b35  pop     rdi
0x180021b36  pop     rsi
0x180021b37  pop     rbp
0x180021b38  pop     rbx
0x180021b39  retn
```
