# IntfStartAutoConfig(void *)

- ea: `0x18001b254`
- end: `0x18001b4db`
- name: `?IntfStartAutoConfig@@YAKPEAX@Z`
- size: `647`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180019c00`

## callees

- `0x1800025f0`
- `0x18000a9c0`
- `0x18000c230`
- `0x18001b254`
- `0x18001bf24`
- `0x180022834`
- `0x180022a6c`

## import_xrefs

- `dot3msm!Dot3MsmInitAdapter` at `0x18001b3d0`
- `dot3msm!Dot3MsmInitAdapter` at `0x18001b3d0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b33c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b33c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b46a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b46a`
- `MobileNetworking!HtDereferenceHandleWithTag` at `0x18001b48e`
- `MobileNetworking!HtDereferenceHandleWithTag` at `0x18001b48e`
- `MobileNetworking!HtReferenceHandleWithTag` at `0x18001b2de`
- `MobileNetworking!HtReferenceHandleWithTag` at `0x18001b2de`

## pseudocode

```c
__int64 __fastcall IntfStartAutoConfig(void *a1)
{
  unsigned int v2; // eax
  unsigned int v3; // ebx
  struct _LIST_ENTRY *v4; // rcx
  unsigned int started; // eax
  __int64 v6; // rcx
  unsigned int inited; // eax
  __int64 v9; // [rsp+40h] [rbp-38h] BYREF
  __int128 v10; // [rsp+48h] [rbp-30h] BYREF
  __int64 v11; // [rsp+58h] [rbp-20h]

  v10 = 0;
  v11 = 0;
  v9 = 0;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 19, WPP_0eee27c7e0cd3271439d8d336f664c32_Traceguids);
  }
  v2 = HtReferenceHandleWithTag(g_hHandleTable, a1, 1229870150, 0, 1, &v9);
  v3 = v2;
  if ( !v2 )
  {
    if ( !*(_DWORD *)(v9 + 168) )
      goto LABEL_27;
    EnterCriticalSection((LPCRITICAL_SECTION)(v9 + 128));
    started = AceStartStateMachine((struct _ACE_STATE_MACHINE *)(v9 + 176));
    v3 = started;
    if ( started )
    {
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control[1].Blink)
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 21, WPP_0eee27c7e0cd3271439d8d336f664c32_Traceguids, started);
      }
    }
    else
    {
      *(_DWORD *)(v9 + 168) = 0;
      v6 = v9;
      if ( !*(_QWORD *)(v9 + 328) )
      {
        v10 = *(_OWORD *)(v9 + 8);
        v11 = *(_QWORD *)(v9 + 120);
        inited = Dot3MsmInitAdapter(a1, &v10, v9 + 328);
        v3 = inited;
        if ( inited )
        {
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && BYTE1(WPP_GLOBAL_Control[1].Blink)
            && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
          {
            WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 22, WPP_0eee27c7e0cd3271439d8d336f664c32_Traceguids, inited);
          }
          if ( (Microsoft_Windows_Wired_AutoConfigEnableBits & 4) != 0 )
            McTemplateU0qqqjz_EtwEventWriteTransfer(
              v9 + 8,
              (unsigned int)IntfInitFailed,
              v3,
              234,
              0,
              v9 + 8,
              *(_QWORD *)(v9 + 120));
          goto LABEL_26;
        }
        v6 = v9;
      }
      AceInsertTrigger((PVOID)(v6 + 176), 1u, 0, 0, 1);
    }
LABEL_26:
    LeaveCriticalSection((LPCRITICAL_SECTION)(v9 + 128));
    goto LABEL_27;
  }
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink)
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 20, WPP_0eee27c7e0cd3271439d8d336f664c32_Traceguids, v2);
LABEL_27:
    v4 = WPP_GLOBAL_Control;
  }
  if ( v9 )
  {
    HtDereferenceHandleWithTag(g_hHandleTable, a1, 0, 1);
    v4 = WPP_GLOBAL_Control;
  }
  if ( v4 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && BYTE1(v4[1].Blink) >= 4u && (BYTE4(v4[1].Blink) & 1) != 0 )
    WPP_SF_d(v4[1].Flink, 23, WPP_0eee27c7e0cd3271439d8d336f664c32_Traceguids, v3);
  return v3;
}

```

## disassembly

```asm
0x18001b254  push    rbp
0x18001b256  push    rbx
0x18001b257  push    rsi
0x18001b258  push    rdi
0x18001b259  push    r12
0x18001b25b  push    r15
0x18001b25d  mov     rbp, rsp
0x18001b260  sub     rsp, 78h
0x18001b264  mov     rax, cs:__security_cookie
0x18001b26b  xor     rax, rsp
0x18001b26e  mov     [rbp+var_18], rax
0x18001b272  xor     eax, eax
0x18001b274  xorps   xmm0, xmm0
0x18001b277  movups  [rbp+var_30], xmm0
0x18001b27b  mov     [rbp+var_20], rax
0x18001b27f  mov     rdi, rcx
0x18001b282  mov     [rbp+var_38], rax
0x18001b286  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b28d  lea     r15, WPP_GLOBAL_Control
0x18001b294  lea     esi, [rax+1]
0x18001b297  lea     r12, WPP_0eee27c7e0cd3271439d8d336f664c32_Traceguids
0x18001b29e  cmp     rcx, r15
0x18001b2a1  jz      short loc_18001B2BE
0x18001b2a3  cmp     byte ptr [rcx+19h], 4
0x18001b2a7  jb      short loc_18001B2BE
0x18001b2a9  test    [rcx+1Ch], sil
0x18001b2ad  jz      short loc_18001B2BE
0x18001b2af  mov     rcx, [rcx+10h]
0x18001b2b3  lea     edx, [rax+13h]
0x18001b2b6  mov     r8, r12
0x18001b2b9  call    WPP_SF_
0x18001b2be  mov     rcx, cs:?g_hHandleTable@@3PEAXEA; void * g_hHandleTable
0x18001b2c5  lea     rax, [rbp+var_38]
0x18001b2c9  mov     [rsp+78h+var_50], rax
0x18001b2ce  xor     r9d, r9d
0x18001b2d1  mov     r8d, 494E5446h
0x18001b2d7  mov     [rsp+78h+var_58], esi
0x18001b2db  mov     rdx, rdi
0x18001b2de  call    cs:__imp_HtReferenceHandleWithTag
0x18001b2e4  mov     ebx, eax
0x18001b2e6  test    eax, eax
0x18001b2e8  jz      short loc_18001B327
0x18001b2ea  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b2f1  cmp     rcx, r15
0x18001b2f4  jz      loc_18001B477
0x18001b2fa  cmp     [rcx+19h], sil
0x18001b2fe  jb      loc_18001B477
0x18001b304  test    [rcx+1Ch], sil
0x18001b308  jz      loc_18001B477
0x18001b30e  mov     rcx, [rcx+10h]
0x18001b312  mov     edx, 14h
0x18001b317  mov     r9d, eax
0x18001b31a  mov     r8, r12
0x18001b31d  call    WPP_SF_d
0x18001b322  jmp     loc_18001B470
0x18001b327  mov     rcx, [rbp+var_38]
0x18001b32b  cmp     dword ptr [rcx+0A8h], 0
0x18001b332  jz      loc_18001B470
0x18001b338  sub     rcx, 0FFFFFFFFFFFFFF80h; lpCriticalSection
0x18001b33c  call    cs:__imp_EnterCriticalSection
0x18001b342  mov     rcx, [rbp+var_38]
0x18001b346  add     rcx, 0B0h; struct _ACE_STATE_MACHINE *
0x18001b34d  call    ?AceStartStateMachine@@YAKPEAU_ACE_STATE_MACHINE@@@Z; AceStartStateMachine(_ACE_STATE_MACHINE *)
0x18001b352  mov     ebx, eax
0x18001b354  test    eax, eax
0x18001b356  jz      short loc_18001B395
0x18001b358  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b35f  cmp     rcx, r15
0x18001b362  jz      loc_18001B462
0x18001b368  cmp     [rcx+19h], sil
0x18001b36c  jb      loc_18001B462
0x18001b372  test    [rcx+1Ch], sil
0x18001b376  jz      loc_18001B462
0x18001b37c  mov     rcx, [rcx+10h]
0x18001b380  mov     edx, 15h
0x18001b385  mov     r9d, eax
0x18001b388  mov     r8, r12
0x18001b38b  call    WPP_SF_d
0x18001b390  jmp     loc_18001B462
0x18001b395  mov     rax, [rbp+var_38]
0x18001b399  mov     dword ptr [rax+0A8h], 0
0x18001b3a3  mov     rcx, [rbp+var_38]
0x18001b3a7  lea     r8, [rcx+148h]
0x18001b3ae  cmp     qword ptr [r8], 0
0x18001b3b2  jnz     loc_18001B44A
0x18001b3b8  movups  xmm0, xmmword ptr [rcx+8]
0x18001b3bc  lea     rdx, [rbp+var_30]
0x18001b3c0  movdqu  [rbp+var_30], xmm0
0x18001b3c5  mov     rax, [rcx+78h]
0x18001b3c9  mov     rcx, rdi
0x18001b3cc  mov     [rbp+var_20], rax
0x18001b3d0  call    cs:__imp_Dot3MsmInitAdapter
0x18001b3d6  mov     ebx, eax
0x18001b3d8  test    eax, eax
0x18001b3da  jz      short loc_18001B446
0x18001b3dc  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b3e3  cmp     rcx, r15
0x18001b3e6  jz      short loc_18001B408
0x18001b3e8  cmp     [rcx+19h], sil
0x18001b3ec  jb      short loc_18001B408
0x18001b3ee  test    [rcx+1Ch], sil
0x18001b3f2  jz      short loc_18001B408
0x18001b3f4  mov     rcx, [rcx+10h]
0x18001b3f8  mov     edx, 16h
0x18001b3fd  mov     r9d, eax
0x18001b400  mov     r8, r12
0x18001b403  call    WPP_SF_d
0x18001b408  test    cs:Microsoft_Windows_Wired_AutoConfigEnableBits, 4
0x18001b40f  jz      short loc_18001B462
0x18001b411  mov     rax, [rbp+var_38]
0x18001b415  lea     rdx, IntfInitFailed
0x18001b41c  mov     r9d, 0EAh
0x18001b422  mov     r8d, ebx
0x18001b425  lea     rcx, [rax+8]
0x18001b429  mov     rax, [rax+78h]
0x18001b42d  mov     [rsp+78h+var_48], rax
0x18001b432  mov     [rsp+78h+var_50], rcx
0x18001b437  mov     [rsp+78h+var_58], 0
0x18001b43f  call    McTemplateU0qqqjz_EtwEventWriteTransfer
0x18001b444  jmp     short loc_18001B462
0x18001b446  mov     rcx, [rbp+var_38]
0x18001b44a  add     rcx, 0B0h; Context
0x18001b451  mov     [rsp+78h+var_58], esi; int
0x18001b455  xor     r9d, r9d; unsigned int
0x18001b458  xor     r8d, r8d; void *
0x18001b45b  mov     edx, esi; unsigned int
0x18001b45d  call    ?AceInsertTrigger@@YAKPEAU_ACE_STATE_MACHINE@@KPEAXKH@Z; AceInsertTrigger(_ACE_STATE_MACHINE *,ulong,void *,ulong,int)
0x18001b462  mov     rcx, [rbp+var_38]
0x18001b466  sub     rcx, 0FFFFFFFFFFFFFF80h; lpCriticalSection
0x18001b46a  call    cs:__imp_LeaveCriticalSection
0x18001b470  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b477  cmp     [rbp+var_38], 0
0x18001b47c  jz      short loc_18001B49B
0x18001b47e  mov     rcx, cs:?g_hHandleTable@@3PEAXEA; void * g_hHandleTable
0x18001b485  mov     r9d, esi
0x18001b488  xor     r8d, r8d
0x18001b48b  mov     rdx, rdi
0x18001b48e  call    cs:__imp_HtDereferenceHandleWithTag
0x18001b494  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b49b  cmp     rcx, r15
0x18001b49e  jz      short loc_18001B4C0
0x18001b4a0  cmp     byte ptr [rcx+19h], 4
0x18001b4a4  jb      short loc_18001B4C0
0x18001b4a6  test    [rcx+1Ch], sil
0x18001b4aa  jz      short loc_18001B4C0
0x18001b4ac  mov     rcx, [rcx+10h]
0x18001b4b0  mov     edx, 17h
0x18001b4b5  mov     r9d, ebx
0x18001b4b8  mov     r8, r12
0x18001b4bb  call    WPP_SF_d
0x18001b4c0  mov     eax, ebx
0x18001b4c2  mov     rcx, [rbp+var_18]
0x18001b4c6  xor     rcx, rsp; StackCookie
0x18001b4c9  call    __security_check_cookie
0x18001b4ce  add     rsp, 78h
0x18001b4d2  pop     r15
0x18001b4d4  pop     r12
0x18001b4d6  pop     rdi
0x18001b4d7  pop     rsi
0x18001b4d8  pop     rbx
0x18001b4d9  pop     rbp
0x18001b4da  retn
```
