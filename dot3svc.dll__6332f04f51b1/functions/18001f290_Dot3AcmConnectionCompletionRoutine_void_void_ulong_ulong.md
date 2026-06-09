# Dot3AcmConnectionCompletionRoutine(void *,void *,ulong,ulong)

- ea: `0x18001f290`
- end: `0x18001f4bd`
- name: `?Dot3AcmConnectionCompletionRoutine@@YAKPEAX0KK@Z`
- size: `557`
- prototype: `__int64 __fastcall(void *, void *, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000a7ec`
- `0x18000a9c0`
- `0x180013264`
- `0x180017224`
- `0x18001834c`
- `0x18001f290`
- `0x180027040`

## import_xrefs

- `MobileNetworking!HtDereferenceHandleWithTag` at `0x18001f46c`
- `MobileNetworking!HtDereferenceHandleWithTag` at `0x18001f46c`
- `MobileNetworking!HtReferenceHandleWithTag` at `0x18001f340`
- `MobileNetworking!HtReferenceHandleWithTag` at `0x18001f340`

## pseudocode

```c
__int64 __fastcall Dot3AcmConnectionCompletionRoutine(void *a1, void *a2, unsigned int a3, unsigned int a4)
{
  struct _LIST_ENTRY *v8; // rcx
  unsigned int v9; // ebx
  unsigned int v10; // ebx
  unsigned int *v11; // rax
  int v12; // edx
  unsigned int *v13; // rdi
  struct _LAN_INTERFACE_CONTEXT *v14; // rax
  GUID v15; // xmm0
  struct _L2_NOTIFICATION_DATA v17; // [rsp+30h] [rbp-30h] BYREF
  struct _LAN_INTERFACE_CONTEXT *v18; // [rsp+90h] [rbp+30h] BYREF
  unsigned int v19; // [rsp+A0h] [rbp+40h] BYREF

  v18 = 0;
  v17.InterfaceGuid = 0;
  *(&v17.dwDataSize + 1) = 0;
  v19 = a3;
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 89, WPP_81374dd11c13362d0a381c62b18e62ba_Traceguids, a3);
    v8 = WPP_GLOBAL_Control;
  }
  if ( !a1 )
  {
    v9 = 87;
    goto LABEL_23;
  }
  v9 = HtReferenceHandleWithTag(g_hHandleTable, a1, 1229870150, 0, 1, &v18);
  if ( v9 )
    goto LABEL_22;
  v10 = 16;
  v11 = (unsigned int *)Dot3Alloc(0x10u);
  v13 = v11;
  if ( v11 )
  {
    *v11 = a4;
    *((_QWORD *)v11 + 1) = a2;
    if ( !a3 && (!a4 || a4 == 458755) )
    {
      v10 = 8;
      *v11 = 0;
    }
    v14 = v18;
    if ( *((_DWORD *)v18 + 106) )
    {
      IntfCompletePlap(v18, v12, a4);
      v14 = v18;
    }
    if ( *((_DWORD *)v14 + 107) )
      LanNotifyCompleteTimely(a3);
    v9 = IntfEventHandler(a1, v10, v13, 0x10u);
    v17.NotificationSource = 1;
    v17.NotificationCode = 4;
    v17.dwDataSize = 4;
    v15 = *(GUID *)((char *)v18 + 8);
    v17.pData = &v19;
    v17.InterfaceGuid = v15;
    NhNotify(0, &v17);
    goto LABEL_22;
  }
  v9 = 8;
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink)
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 90, WPP_81374dd11c13362d0a381c62b18e62ba_Traceguids, 8);
LABEL_22:
    v8 = WPP_GLOBAL_Control;
  }
LABEL_23:
  if ( v18 )
  {
    HtDereferenceHandleWithTag(g_hHandleTable, a1, 0, 1);
    v8 = WPP_GLOBAL_Control;
  }
  if ( v8 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && BYTE1(v8[1].Blink) >= 4u && (BYTE4(v8[1].Blink) & 1) != 0 )
    WPP_SF_d(v8[1].Flink, 91, WPP_81374dd11c13362d0a381c62b18e62ba_Traceguids, v9);
  return v9;
}

```

## disassembly

```asm
0x18001f290  mov     [rsp-28h+arg_8], rbx
0x18001f295  mov     [rsp-28h+arg_18], rsi
0x18001f29a  push    rbp
0x18001f29b  push    rdi
0x18001f29c  push    r12
0x18001f29e  push    r14
0x18001f2a0  push    r15
0x18001f2a2  mov     rbp, rsp
0x18001f2a5  sub     rsp, 60h
0x18001f2a9  xorps   xmm0, xmm0
0x18001f2ac  mov     [rbp+arg_0], 0
0x18001f2b4  movdqu  xmmword ptr [rbp+var_30.InterfaceGuid.Data1], xmm0
0x18001f2b9  mov     esi, r9d
0x18001f2bc  mov     dword ptr [rbp+var_30+1Ch], 0
0x18001f2c3  mov     r14d, r8d
0x18001f2c6  mov     [rbp+arg_10], r8d
0x18001f2ca  mov     r12, rdx
0x18001f2cd  mov     r15, rcx
0x18001f2d0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f2d7  lea     rdi, WPP_GLOBAL_Control
0x18001f2de  cmp     rcx, rdi
0x18001f2e1  jz      short loc_18001F30E
0x18001f2e3  cmp     byte ptr [rcx+19h], 4
0x18001f2e7  jb      short loc_18001F30E
0x18001f2e9  test    byte ptr [rcx+1Ch], 1
0x18001f2ed  jz      short loc_18001F30E
0x18001f2ef  mov     rcx, [rcx+10h]
0x18001f2f3  mov     r9d, r8d
0x18001f2f6  lea     r8, WPP_81374dd11c13362d0a381c62b18e62ba_Traceguids
0x18001f2fd  mov     edx, 59h ; 'Y'
0x18001f302  call    WPP_SF_d
0x18001f307  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f30e  test    r15, r15
0x18001f311  jnz     short loc_18001F31C
0x18001f313  lea     ebx, [r15+57h]
0x18001f317  jmp     loc_18001F452
0x18001f31c  mov     rcx, cs:?g_hHandleTable@@3PEAXEA; void * g_hHandleTable
0x18001f323  lea     rax, [rbp+arg_0]
0x18001f327  mov     [rsp+60h+var_38], rax
0x18001f32c  xor     r9d, r9d
0x18001f32f  mov     r8d, 494E5446h
0x18001f335  mov     [rsp+60h+var_40], 1
0x18001f33d  mov     rdx, r15
0x18001f340  call    cs:__imp_HtReferenceHandleWithTag
0x18001f346  mov     ebx, eax
0x18001f348  test    eax, eax
0x18001f34a  jnz     loc_18001F44B
0x18001f350  lea     ebx, [rax+10h]
0x18001f353  mov     ecx, ebx; dwBytes
0x18001f355  call    ?Dot3Alloc@@YAPEAX_K@Z; Dot3Alloc(unsigned __int64)
0x18001f35a  mov     rdi, rax
0x18001f35d  test    rax, rax
0x18001f360  jnz     short loc_18001F3AB
0x18001f362  lea     ebx, [rax+8]
0x18001f365  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f36c  lea     rdi, WPP_GLOBAL_Control
0x18001f373  cmp     rcx, rdi
0x18001f376  jz      loc_18001F452
0x18001f37c  cmp     byte ptr [rcx+19h], 1
0x18001f380  jb      loc_18001F452
0x18001f386  test    byte ptr [rcx+1Ch], 1
0x18001f38a  jz      loc_18001F452
0x18001f390  mov     rcx, [rcx+10h]
0x18001f394  lea     edx, [rax+5Ah]
0x18001f397  mov     r9d, ebx
0x18001f39a  lea     r8, WPP_81374dd11c13362d0a381c62b18e62ba_Traceguids
0x18001f3a1  call    WPP_SF_d
0x18001f3a6  jmp     loc_18001F44B
0x18001f3ab  mov     [rax], esi
0x18001f3ad  mov     [rax+8], r12
0x18001f3b1  test    r14d, r14d
0x18001f3b4  jnz     short loc_18001F3CD
0x18001f3b6  test    esi, esi
0x18001f3b8  jz      short loc_18001F3C2
0x18001f3ba  cmp     esi, 70003h
0x18001f3c0  jnz     short loc_18001F3CD
0x18001f3c2  mov     ebx, 8
0x18001f3c7  mov     dword ptr [rax], 0
0x18001f3cd  mov     rax, [rbp+arg_0]
0x18001f3d1  cmp     dword ptr [rax+1A8h], 0
0x18001f3d8  jz      short loc_18001F3E9
0x18001f3da  mov     r8d, esi; unsigned int
0x18001f3dd  mov     rcx, rax; struct _LAN_INTERFACE_CONTEXT *
0x18001f3e0  call    ?IntfCompletePlap@@YAKPEAU_LAN_INTERFACE_CONTEXT@@HK@Z; IntfCompletePlap(_LAN_INTERFACE_CONTEXT *,int,ulong)
0x18001f3e5  mov     rax, [rbp+arg_0]
0x18001f3e9  cmp     dword ptr [rax+1ACh], 0
0x18001f3f0  jz      short loc_18001F3FA
0x18001f3f2  mov     ecx, r14d
0x18001f3f5  call    LanNotifyCompleteTimely
0x18001f3fa  mov     r9d, 10h; unsigned int
0x18001f400  mov     r8, rdi; void *
0x18001f403  mov     edx, ebx; unsigned int
0x18001f405  mov     rcx, r15; void *
0x18001f408  call    ?IntfEventHandler@@YAKPEAXK0K@Z; IntfEventHandler(void *,ulong,void *,ulong)
0x18001f40d  mov     ebx, eax
0x18001f40f  mov     [rbp+var_30.NotificationSource], 1
0x18001f416  mov     rax, [rbp+arg_0]
0x18001f41a  lea     rdx, [rbp+var_30]; struct _L2_NOTIFICATION_DATA *
0x18001f41e  xor     ecx, ecx; void *
0x18001f420  mov     [rbp+var_30.NotificationCode], 4
0x18001f427  mov     [rbp+var_30.dwDataSize], 4
0x18001f42e  movups  xmm0, xmmword ptr [rax+8]
0x18001f432  lea     rax, [rbp+arg_10]
0x18001f436  mov     [rbp+var_30.pData], rax
0x18001f43a  movdqu  xmmword ptr [rbp+var_30.InterfaceGuid.Data1], xmm0
0x18001f43f  call    ?NhNotify@@YAKPEAXPEAU_L2_NOTIFICATION_DATA@@@Z; NhNotify(void *,_L2_NOTIFICATION_DATA *)
0x18001f444  lea     rdi, WPP_GLOBAL_Control
0x18001f44b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f452  cmp     [rbp+arg_0], 0
0x18001f457  jz      short loc_18001F479
0x18001f459  mov     rcx, cs:?g_hHandleTable@@3PEAXEA; void * g_hHandleTable
0x18001f460  mov     r9d, 1
0x18001f466  xor     r8d, r8d
0x18001f469  mov     rdx, r15
0x18001f46c  call    cs:__imp_HtDereferenceHandleWithTag
0x18001f472  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f479  cmp     rcx, rdi
0x18001f47c  jz      short loc_18001F4A2
0x18001f47e  cmp     byte ptr [rcx+19h], 4
0x18001f482  jb      short loc_18001F4A2
0x18001f484  test    byte ptr [rcx+1Ch], 1
0x18001f488  jz      short loc_18001F4A2
0x18001f48a  mov     rcx, [rcx+10h]
0x18001f48e  lea     r8, WPP_81374dd11c13362d0a381c62b18e62ba_Traceguids
0x18001f495  mov     edx, 5Bh ; '['
0x18001f49a  mov     r9d, ebx
0x18001f49d  call    WPP_SF_d
0x18001f4a2  lea     r11, [rsp+60h+var_s0]
0x18001f4a7  mov     eax, ebx
0x18001f4a9  mov     rbx, [r11+38h]
0x18001f4ad  mov     rsi, [r11+48h]
0x18001f4b1  mov     rsp, r11
0x18001f4b4  pop     r15
0x18001f4b6  pop     r14
0x18001f4b8  pop     r12
0x18001f4ba  pop     rdi
0x18001f4bb  pop     rbp
0x18001f4bc  retn
```
