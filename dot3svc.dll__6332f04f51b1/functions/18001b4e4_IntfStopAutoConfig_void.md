# IntfStopAutoConfig(void *)

- ea: `0x18001b4e4`
- end: `0x18001b7ae`
- name: `?IntfStopAutoConfig@@YAKPEAX@Z`
- size: `714`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180019c00`

## callees

- `0x18000a9c0`
- `0x18000c230`
- `0x180016c1c`
- `0x18001b4e4`
- `0x180022c54`
- `0x18002489c`
- `0x18002491c`
- `0x180033d14`

## import_xrefs

- `dot3msm!Dot3SetPortAuthenticationState` at `0x18001b6ad`
- `dot3msm!Dot3SetPortAuthenticationState` at `0x18001b6ad`
- `dot3msm!Dot3MsmDeInitAdapter` at `0x18001b6eb`
- `dot3msm!Dot3MsmDeInitAdapter` at `0x18001b6eb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b5c1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b5c1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b745`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b745`
- `MobileNetworking!HtDereferenceHandleWithTag` at `0x18001b769`
- `MobileNetworking!HtDereferenceHandleWithTag` at `0x18001b769`
- `MobileNetworking!HtReferenceHandleWithTag` at `0x18001b563`
- `MobileNetworking!HtReferenceHandleWithTag` at `0x18001b563`

## pseudocode

```c
__int64 __fastcall IntfStopAutoConfig(void *a1)
{
  unsigned int v2; // eax
  unsigned int v3; // ebx
  struct _LIST_ENTRY *v4; // rcx
  unsigned int v5; // eax
  struct _LIST_ENTRY *v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // rax
  void *v9; // rcx
  __int64 v10; // r9
  tagNETCON_STATUS v12; // [rsp+68h] [rbp+38h] BYREF
  __int64 v13; // [rsp+70h] [rbp+40h] BYREF

  v12 = NCS_DISCONNECTED;
  v13 = 0;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 24, WPP_0eee27c7e0cd3271439d8d336f664c32_Traceguids);
  }
  v2 = HtReferenceHandleWithTag(g_hHandleTable, a1, 1229870150, 0, 1, &v13);
  v3 = v2;
  if ( !v2 )
  {
    if ( *(_DWORD *)(v13 + 168) )
      goto LABEL_37;
    EnterCriticalSection((LPCRITICAL_SECTION)(v13 + 128));
    v5 = AceStopStateMachine((struct _ACE_STATE_MACHINE *)(v13 + 176));
    v3 = v5;
    if ( v5 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || !BYTE1(WPP_GLOBAL_Control[1].Blink)
        || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
      {
        goto LABEL_36;
      }
      v7 = 26;
    }
    else
    {
      v5 = ChangeNdisControlState((struct _GUID *)(v13 + 8), 0);
      v3 = v5;
      if ( v5 )
      {
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          || !BYTE1(WPP_GLOBAL_Control[1].Blink)
          || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
        {
          goto LABEL_36;
        }
        v7 = 27;
      }
      else
      {
        v5 = ChangeNdisAuthState((struct _GUID *)(v13 + 8), 1);
        v3 = v5;
        if ( v5 )
        {
          v6 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            || !BYTE1(WPP_GLOBAL_Control[1].Blink)
            || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
          {
            goto LABEL_36;
          }
          v7 = 28;
        }
        else
        {
          v5 = Dot3SetPortAuthenticationState(*(_QWORD *)(v13 + 328), 0, 1);
          v3 = v5;
          if ( !v5 )
          {
            v8 = v13;
            if ( *(_QWORD *)(v13 + 328) )
            {
              Dot3MsmDeInitAdapter();
              *(_QWORD *)(v13 + 328) = 0;
              v8 = v13;
            }
            *(_DWORD *)(v8 + 168) = 1;
            *(_DWORD *)(v13 + 288) = 1;
            v3 = ConvertToNCSState(*(unsigned int *)(v13 + 288), &v12);
            if ( !v3 )
              v3 = Dot3ConnectionStatusChanged(v9, (const struct _GUID *)(v10 + 8), v12);
            goto LABEL_36;
          }
          v6 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            || !BYTE1(WPP_GLOBAL_Control[1].Blink)
            || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
          {
LABEL_36:
            LeaveCriticalSection((LPCRITICAL_SECTION)(v13 + 128));
            goto LABEL_37;
          }
          v7 = 29;
        }
      }
    }
    WPP_SF_d(v6[1].Flink, v7, WPP_0eee27c7e0cd3271439d8d336f664c32_Traceguids, v5);
    goto LABEL_36;
  }
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink)
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 25, WPP_0eee27c7e0cd3271439d8d336f664c32_Traceguids, v2);
LABEL_37:
    v4 = WPP_GLOBAL_Control;
  }
  if ( v13 )
  {
    HtDereferenceHandleWithTag(g_hHandleTable, a1, 0, 1);
    v4 = WPP_GLOBAL_Control;
  }
  if ( v4 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && BYTE1(v4[1].Blink) >= 4u && (BYTE4(v4[1].Blink) & 1) != 0 )
    WPP_SF_d(v4[1].Flink, 30, WPP_0eee27c7e0cd3271439d8d336f664c32_Traceguids, v3);
  return v3;
}

```

## disassembly

```asm
0x18001b4e4  mov     [rsp-28h+arg_0], rbx
0x18001b4e9  push    rbp
0x18001b4ea  push    rsi
0x18001b4eb  push    rdi
0x18001b4ec  push    r12
0x18001b4ee  push    r15
0x18001b4f0  mov     rbp, rsp
0x18001b4f3  sub     rsp, 30h
0x18001b4f7  mov     rdi, rcx
0x18001b4fa  mov     [rbp+arg_8], 0
0x18001b501  mov     [rbp+arg_10], 0
0x18001b509  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b510  lea     r15, WPP_GLOBAL_Control
0x18001b517  lea     r12, WPP_0eee27c7e0cd3271439d8d336f664c32_Traceguids
0x18001b51e  mov     esi, 1
0x18001b523  cmp     rcx, r15
0x18001b526  jz      short loc_18001B543
0x18001b528  cmp     byte ptr [rcx+19h], 4
0x18001b52c  jb      short loc_18001B543
0x18001b52e  test    [rcx+1Ch], sil
0x18001b532  jz      short loc_18001B543
0x18001b534  mov     rcx, [rcx+10h]
0x18001b538  lea     edx, [rsi+17h]
0x18001b53b  mov     r8, r12
0x18001b53e  call    WPP_SF_
0x18001b543  mov     rcx, cs:?g_hHandleTable@@3PEAXEA; void * g_hHandleTable
0x18001b54a  lea     rax, [rbp+arg_10]
0x18001b54e  mov     [rsp+30h+var_8], rax
0x18001b553  xor     r9d, r9d
0x18001b556  mov     r8d, 494E5446h
0x18001b55c  mov     [rsp+30h+var_10], esi
0x18001b560  mov     rdx, rdi
0x18001b563  call    cs:__imp_HtReferenceHandleWithTag
0x18001b569  mov     ebx, eax
0x18001b56b  test    eax, eax
0x18001b56d  jz      short loc_18001B5AC
0x18001b56f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b576  cmp     rcx, r15
0x18001b579  jz      loc_18001B752
0x18001b57f  cmp     [rcx+19h], sil
0x18001b583  jb      loc_18001B752
0x18001b589  test    [rcx+1Ch], sil
0x18001b58d  jz      loc_18001B752
0x18001b593  mov     rcx, [rcx+10h]
0x18001b597  mov     edx, 19h
0x18001b59c  mov     r9d, eax
0x18001b59f  mov     r8, r12
0x18001b5a2  call    WPP_SF_d
0x18001b5a7  jmp     loc_18001B74B
0x18001b5ac  mov     rcx, [rbp+arg_10]
0x18001b5b0  cmp     dword ptr [rcx+0A8h], 0
0x18001b5b7  jnz     loc_18001B74B
0x18001b5bd  sub     rcx, 0FFFFFFFFFFFFFF80h; lpCriticalSection
0x18001b5c1  call    cs:__imp_EnterCriticalSection
0x18001b5c7  mov     rcx, [rbp+arg_10]
0x18001b5cb  add     rcx, 0B0h; struct _ACE_STATE_MACHINE *
0x18001b5d2  call    ?AceStopStateMachine@@YAKPEAU_ACE_STATE_MACHINE@@@Z; AceStopStateMachine(_ACE_STATE_MACHINE *)
0x18001b5d7  mov     ebx, eax
0x18001b5d9  test    eax, eax
0x18001b5db  jz      short loc_18001B61A
0x18001b5dd  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b5e4  cmp     rcx, r15
0x18001b5e7  jz      loc_18001B73D
0x18001b5ed  cmp     [rcx+19h], sil
0x18001b5f1  jb      loc_18001B73D
0x18001b5f7  test    [rcx+1Ch], sil
0x18001b5fb  jz      loc_18001B73D
0x18001b601  mov     edx, 1Ah
0x18001b606  mov     rcx, [rcx+10h]
0x18001b60a  mov     r9d, eax
0x18001b60d  mov     r8, r12
0x18001b610  call    WPP_SF_d
0x18001b615  jmp     loc_18001B73D
0x18001b61a  mov     rcx, [rbp+arg_10]
0x18001b61e  xor     edx, edx; int
0x18001b620  add     rcx, 8; struct _GUID *
0x18001b624  call    ?ChangeNdisControlState@@YAKPEAU_GUID@@H@Z; ChangeNdisControlState(_GUID *,int)
0x18001b629  mov     ebx, eax
0x18001b62b  test    eax, eax
0x18001b62d  jz      short loc_18001B65A
0x18001b62f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b636  cmp     rcx, r15
0x18001b639  jz      loc_18001B73D
0x18001b63f  cmp     [rcx+19h], sil
0x18001b643  jb      loc_18001B73D
0x18001b649  test    [rcx+1Ch], sil
0x18001b64d  jz      loc_18001B73D
0x18001b653  mov     edx, 1Bh
0x18001b658  jmp     short loc_18001B606
0x18001b65a  mov     rcx, [rbp+arg_10]
0x18001b65e  mov     edx, esi; int
0x18001b660  add     rcx, 8; struct _GUID *
0x18001b664  call    ?ChangeNdisAuthState@@YAKPEAU_GUID@@H@Z; ChangeNdisAuthState(_GUID *,int)
0x18001b669  mov     ebx, eax
0x18001b66b  test    eax, eax
0x18001b66d  jz      short loc_18001B69D
0x18001b66f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b676  cmp     rcx, r15
0x18001b679  jz      loc_18001B73D
0x18001b67f  cmp     [rcx+19h], sil
0x18001b683  jb      loc_18001B73D
0x18001b689  test    [rcx+1Ch], sil
0x18001b68d  jz      loc_18001B73D
0x18001b693  mov     edx, 1Ch
0x18001b698  jmp     loc_18001B606
0x18001b69d  mov     rcx, [rbp+arg_10]
0x18001b6a1  mov     r8d, esi
0x18001b6a4  xor     edx, edx
0x18001b6a6  mov     rcx, [rcx+148h]
0x18001b6ad  call    cs:__imp_Dot3SetPortAuthenticationState
0x18001b6b3  mov     ebx, eax
0x18001b6b5  test    eax, eax
0x18001b6b7  jz      short loc_18001B6DB
0x18001b6b9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b6c0  cmp     rcx, r15
0x18001b6c3  jz      short loc_18001B73D
0x18001b6c5  cmp     [rcx+19h], sil
0x18001b6c9  jb      short loc_18001B73D
0x18001b6cb  test    [rcx+1Ch], sil
0x18001b6cf  jz      short loc_18001B73D
0x18001b6d1  mov     edx, 1Dh
0x18001b6d6  jmp     loc_18001B606
0x18001b6db  mov     rax, [rbp+arg_10]
0x18001b6df  mov     rcx, [rax+148h]
0x18001b6e6  test    rcx, rcx
0x18001b6e9  jz      short loc_18001B704
0x18001b6eb  call    cs:__imp_Dot3MsmDeInitAdapter
0x18001b6f1  mov     rax, [rbp+arg_10]
0x18001b6f5  mov     qword ptr [rax+148h], 0
0x18001b700  mov     rax, [rbp+arg_10]
0x18001b704  mov     [rax+0A8h], esi
0x18001b70a  lea     rdx, [rbp+arg_8]
0x18001b70e  mov     rax, [rbp+arg_10]
0x18001b712  mov     [rax+120h], esi
0x18001b718  mov     r9, [rbp+arg_10]
0x18001b71c  mov     ecx, [r9+120h]
0x18001b723  call    ?ConvertToNCSState@@YAKW4_DOT3_AC_STATE@@PEAW4tagNETCON_STATUS@@@Z; ConvertToNCSState(_DOT3_AC_STATE,tagNETCON_STATUS *)
0x18001b728  mov     ebx, eax
0x18001b72a  test    eax, eax
0x18001b72c  jnz     short loc_18001B73D
0x18001b72e  mov     r8d, [rbp+arg_8]; enum tagNETCON_STATUS
0x18001b732  lea     rdx, [r9+8]; struct _GUID *
0x18001b736  call    ?Dot3ConnectionStatusChanged@@YAJPEAXPEBU_GUID@@W4tagNETCON_STATUS@@@Z; Dot3ConnectionStatusChanged(void *,_GUID const *,tagNETCON_STATUS)
0x18001b73b  mov     ebx, eax
0x18001b73d  mov     rcx, [rbp+arg_10]
0x18001b741  sub     rcx, 0FFFFFFFFFFFFFF80h; lpCriticalSection
0x18001b745  call    cs:__imp_LeaveCriticalSection
0x18001b74b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b752  cmp     [rbp+arg_10], 0
0x18001b757  jz      short loc_18001B776
0x18001b759  mov     rcx, cs:?g_hHandleTable@@3PEAXEA; void * g_hHandleTable
0x18001b760  mov     r9d, esi
0x18001b763  xor     r8d, r8d
0x18001b766  mov     rdx, rdi
0x18001b769  call    cs:__imp_HtDereferenceHandleWithTag
0x18001b76f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b776  cmp     rcx, r15
0x18001b779  jz      short loc_18001B79B
0x18001b77b  cmp     byte ptr [rcx+19h], 4
0x18001b77f  jb      short loc_18001B79B
0x18001b781  test    [rcx+1Ch], sil
0x18001b785  jz      short loc_18001B79B
0x18001b787  mov     rcx, [rcx+10h]
0x18001b78b  mov     edx, 1Eh
0x18001b790  mov     r9d, ebx
0x18001b793  mov     r8, r12
0x18001b796  call    WPP_SF_d
0x18001b79b  mov     eax, ebx
0x18001b79d  mov     rbx, [rsp+30h+arg_0]
0x18001b7a2  add     rsp, 30h
0x18001b7a6  pop     r15
0x18001b7a8  pop     r12
0x18001b7aa  pop     rdi
0x18001b7ab  pop     rsi
0x18001b7ac  pop     rbp
0x18001b7ad  retn
```
