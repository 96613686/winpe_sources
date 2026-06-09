# IntfEnableAutoConfig(void *,int)

- ea: `0x180018160`
- end: `0x180018345`
- name: `?IntfEnableAutoConfig@@YAKPEAXH@Z`
- size: `485`
- prototype: `__int64 __fastcall(void *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18002114c`

## callees

- `0x18000a9c0`
- `0x18000c230`
- `0x18001060c`
- `0x180013264`
- `0x180018160`
- `0x18001adc0`
- `0x180024efc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018262`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018262`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800182c0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800182c0`
- `MobileNetworking!HtDereferenceHandleWithTag` at `0x1800182f4`
- `MobileNetworking!HtDereferenceHandleWithTag` at `0x1800182f4`
- `MobileNetworking!HtReferenceHandleWithTag` at `0x18001820e`
- `MobileNetworking!HtReferenceHandleWithTag` at `0x18001820e`

## pseudocode

```c
__int64 __fastcall IntfEnableAutoConfig(void *a1, int a2)
{
  unsigned int v4; // ebx
  unsigned int v5; // eax
  struct _LIST_ENTRY *v6; // rcx
  int v7; // edi
  struct _LAN_INTERFACE_CONTEXT *v8; // rcx
  GUID v9; // xmm0
  __int128 v11; // [rsp+30h] [rbp-40h] BYREF
  int v12; // [rsp+40h] [rbp-30h]
  struct _L2_NOTIFICATION_DATA v13; // [rsp+48h] [rbp-28h] BYREF
  struct _LAN_INTERFACE_CONTEXT *v14; // [rsp+B0h] [rbp+40h] BYREF

  v14 = 0;
  v12 = 0;
  v11 = 0;
  memset(&v13, 0, sizeof(v13));
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 110, WPP_0eee27c7e0cd3271439d8d336f664c32_Traceguids);
  }
  if ( !WimGetGPSettings((struct _LAN_GP_SETTINGS *)&v11) )
  {
    v4 = 5;
LABEL_16:
    v6 = WPP_GLOBAL_Control;
    goto LABEL_17;
  }
  v5 = HtReferenceHandleWithTag(g_hHandleTable, a1, 1229870150, 0, 1, &v14);
  v4 = v5;
  if ( !v5 )
  {
    v7 = 0;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)v14 + 128));
    v8 = v14;
    if ( *((_DWORD *)v14 + 43) != a2 )
    {
      *((_DWORD *)v14 + 43) = a2;
      v7 = 1;
      v13.NotificationSource = 1;
      v9 = *(GUID *)((char *)v14 + 8);
      v13.NotificationCode = 14 - (a2 != 0);
      v13.InterfaceGuid = v9;
      IntfSaveToRegistry(v14);
      Dot3LogAdapterStateEvent(
        (struct _GUID *)((char *)v14 + 8),
        *((unsigned __int16 **)v14 + 15),
        *((_DWORD *)v14 + 43));
      v8 = v14;
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v8 + 128));
    if ( v7 )
      NhNotify(a1, &v13);
    goto LABEL_16;
  }
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink)
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 111, WPP_0eee27c7e0cd3271439d8d336f664c32_Traceguids, v5);
    goto LABEL_16;
  }
LABEL_17:
  if ( v14 )
  {
    HtDereferenceHandleWithTag(g_hHandleTable, a1, 0, 1);
    v6 = WPP_GLOBAL_Control;
  }
  if ( v6 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && BYTE1(v6[1].Blink) >= 4u && (BYTE4(v6[1].Blink) & 1) != 0 )
    WPP_SF_d(v6[1].Flink, 112, WPP_0eee27c7e0cd3271439d8d336f664c32_Traceguids, v4);
  return v4;
}

```

## disassembly

```asm
0x180018160  mov     [rsp-28h+arg_0], rbx
0x180018165  mov     [rsp-28h+arg_8], rsi
0x18001816a  push    rbp
0x18001816b  push    rdi
0x18001816c  push    r12
0x18001816e  push    r14
0x180018170  push    r15
0x180018172  mov     rbp, rsp
0x180018175  sub     rsp, 70h
0x180018179  xor     eax, eax
0x18001817b  mov     [rbp+arg_10], 0
0x180018183  xorps   xmm1, xmm1
0x180018186  mov     [rbp+var_30], eax
0x180018189  xorps   xmm0, xmm0
0x18001818c  mov     [rbp+var_28.pData], rax
0x180018190  movups  [rbp+var_40], xmm0
0x180018194  mov     r14d, edx
0x180018197  mov     rsi, rcx
0x18001819a  movups  xmmword ptr [rbp+var_28.NotificationSource], xmm1
0x18001819e  movups  xmmword ptr [rbp+var_28.InterfaceGuid.Data4], xmm1
0x1800181a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800181a9  lea     r12, WPP_GLOBAL_Control
0x1800181b0  lea     r15d, [rax+1]
0x1800181b4  cmp     rcx, r12
0x1800181b7  jz      short loc_1800181D8
0x1800181b9  cmp     byte ptr [rcx+19h], 4
0x1800181bd  jb      short loc_1800181D8
0x1800181bf  test    [rcx+1Ch], r15b
0x1800181c3  jz      short loc_1800181D8
0x1800181c5  mov     rcx, [rcx+10h]
0x1800181c9  lea     edx, [rax+6Eh]
0x1800181cc  lea     r8, WPP_0eee27c7e0cd3271439d8d336f664c32_Traceguids
0x1800181d3  call    WPP_SF_
0x1800181d8  lea     rcx, [rbp+var_40]; struct _LAN_GP_SETTINGS *
0x1800181dc  call    ?WimGetGPSettings@@YAKPEAU_LAN_GP_SETTINGS@@@Z; WimGetGPSettings(_LAN_GP_SETTINGS *)
0x1800181e1  test    eax, eax
0x1800181e3  jnz     short loc_1800181ED
0x1800181e5  lea     ebx, [rax+5]
0x1800181e8  jmp     loc_1800182D6
0x1800181ed  mov     rcx, cs:?g_hHandleTable@@3PEAXEA; void * g_hHandleTable
0x1800181f4  lea     rax, [rbp+arg_10]
0x1800181f8  mov     [rsp+70h+var_48], rax
0x1800181fd  xor     r9d, r9d
0x180018200  mov     r8d, 494E5446h
0x180018206  mov     [rsp+70h+var_50], r15d
0x18001820b  mov     rdx, rsi
0x18001820e  call    cs:__imp_HtReferenceHandleWithTag
0x180018214  mov     ebx, eax
0x180018216  test    eax, eax
0x180018218  jz      short loc_180018258
0x18001821a  mov     rcx, cs:WPP_GLOBAL_Control
0x180018221  cmp     rcx, r12
0x180018224  jz      loc_1800182DD
0x18001822a  cmp     [rcx+19h], r15b
0x18001822e  jb      loc_1800182DD
0x180018234  test    [rcx+1Ch], r15b
0x180018238  jz      loc_1800182DD
0x18001823e  mov     rcx, [rcx+10h]
0x180018242  lea     r8, WPP_0eee27c7e0cd3271439d8d336f664c32_Traceguids
0x180018249  mov     edx, 6Fh ; 'o'
0x18001824e  mov     r9d, eax
0x180018251  call    WPP_SF_d
0x180018256  jmp     short loc_1800182D6
0x180018258  mov     rcx, [rbp+arg_10]
0x18001825c  xor     edi, edi
0x18001825e  sub     rcx, 0FFFFFFFFFFFFFF80h; lpCriticalSection
0x180018262  call    cs:__imp_EnterCriticalSection
0x180018268  mov     rcx, [rbp+arg_10]
0x18001826c  cmp     [rcx+0ACh], r14d
0x180018273  jz      short loc_1800182BC
0x180018275  mov     [rcx+0ACh], r14d
0x18001827c  mov     edi, r15d
0x18001827f  mov     rcx, [rbp+arg_10]; struct _LAN_INTERFACE_CONTEXT *
0x180018283  neg     r14d
0x180018286  mov     [rbp+var_28.NotificationSource], r15d
0x18001828a  sbb     eax, eax
0x18001828c  add     eax, 0Eh
0x18001828f  movups  xmm0, xmmword ptr [rcx+8]
0x180018293  mov     [rbp+var_28.NotificationCode], eax
0x180018296  movdqu  xmmword ptr [rbp+var_28.InterfaceGuid.Data1], xmm0
0x18001829b  call    ?IntfSaveToRegistry@@YAKPEAU_LAN_INTERFACE_CONTEXT@@@Z; IntfSaveToRegistry(_LAN_INTERFACE_CONTEXT *)
0x1800182a0  mov     rdx, [rbp+arg_10]
0x1800182a4  mov     r8d, [rdx+0ACh]; unsigned int
0x1800182ab  lea     rcx, [rdx+8]; struct _GUID *
0x1800182af  mov     rdx, [rdx+78h]; unsigned __int16 *
0x1800182b3  call    ?Dot3LogAdapterStateEvent@@YAKPEAU_GUID@@PEAGK@Z; Dot3LogAdapterStateEvent(_GUID *,ushort *,ulong)
0x1800182b8  mov     rcx, [rbp+arg_10]
0x1800182bc  sub     rcx, 0FFFFFFFFFFFFFF80h; lpCriticalSection
0x1800182c0  call    cs:__imp_LeaveCriticalSection
0x1800182c6  test    edi, edi
0x1800182c8  jz      short loc_1800182D6
0x1800182ca  lea     rdx, [rbp+var_28]; struct _L2_NOTIFICATION_DATA *
0x1800182ce  mov     rcx, rsi; void *
0x1800182d1  call    ?NhNotify@@YAKPEAXPEAU_L2_NOTIFICATION_DATA@@@Z; NhNotify(void *,_L2_NOTIFICATION_DATA *)
0x1800182d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800182dd  cmp     [rbp+arg_10], 0
0x1800182e2  jz      short loc_180018301
0x1800182e4  mov     rcx, cs:?g_hHandleTable@@3PEAXEA; void * g_hHandleTable
0x1800182eb  mov     r9d, r15d
0x1800182ee  xor     r8d, r8d
0x1800182f1  mov     rdx, rsi
0x1800182f4  call    cs:__imp_HtDereferenceHandleWithTag
0x1800182fa  mov     rcx, cs:WPP_GLOBAL_Control
0x180018301  cmp     rcx, r12
0x180018304  jz      short loc_18001832A
0x180018306  cmp     byte ptr [rcx+19h], 4
0x18001830a  jb      short loc_18001832A
0x18001830c  test    [rcx+1Ch], r15b
0x180018310  jz      short loc_18001832A
0x180018312  mov     rcx, [rcx+10h]
0x180018316  lea     r8, WPP_0eee27c7e0cd3271439d8d336f664c32_Traceguids
0x18001831d  mov     edx, 70h ; 'p'
0x180018322  mov     r9d, ebx
0x180018325  call    WPP_SF_d
0x18001832a  lea     r11, [rsp+70h+var_s0]
0x18001832f  mov     eax, ebx
0x180018331  mov     rbx, [r11+30h]
0x180018335  mov     rsi, [r11+38h]
0x180018339  mov     rsp, r11
0x18001833c  pop     r15
0x18001833e  pop     r14
0x180018340  pop     r12
0x180018342  pop     rdi
0x180018343  pop     rbp
0x180018344  retn
```
