# NcaSrcLnkdTriggerRegisterWait

- ea: `0x18000b1e8`
- end: `0x18000b338`
- name: `NcaSrcLnkdTriggerRegisterWait`
- size: `336`
- prototype: `__int64 __fastcall(int, struct _RTL_CRITICAL_SECTION *, struct _LIST_ENTRY *, void (__stdcall *)(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WAIT Wait, TP_WAIT_RESULT WaitResult), PVOID pv, struct _LIST_ENTRY **)`
- caller_count: `9`
- callee_count: `7`
- tags: ``

## callers

- `0x180006940`
- `0x18000db28`
- `0x18000df10`
- `0x18000e984`
- `0x180010430`
- `0x180010820`
- `0x180011744`
- `0x180014330`
- `0x180014900`

## callees

- `0x180004f04`
- `0x180004f34`
- `0x18000b064`
- `0x18000b1e8`
- `0x18000b3a8`
- `0x18000b51c`
- `0x18001abd4`

## pseudocode

```c
__int64 __fastcall NcaSrcLnkdTriggerRegisterWait(
        int a1,
        struct _RTL_CRITICAL_SECTION *a2,
        struct _LIST_ENTRY *a3,
        void (__stdcall *a4)(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WAIT Wait, TP_WAIT_RESULT WaitResult),
        PVOID pv,
        struct _LIST_ENTRY **a6)
{
  struct _LIST_ENTRY *v10; // rax
  struct _LIST_ENTRY *v11; // rdi
  unsigned int v12; // ebx
  PVOID *v13; // rcx
  unsigned int v14; // eax
  int v15; // eax

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_3bebb8bd632b3e04288e9ea9721fbba3_Traceguids);
  v10 = (struct _LIST_ENTRY *)NcaAlloc(0x30u);
  v11 = v10;
  if ( v10 )
  {
    LODWORD(v10[1].Flink) = a1;
    if ( a3 )
    {
      v12 = 0;
      v10[1].Blink = a3;
      v15 = 0;
    }
    else
    {
      v14 = NcaTriggerRegisterWait(a4, pv);
      v12 = v14;
      if ( v14 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_3bebb8bd632b3e04288e9ea9721fbba3_Traceguids, v14);
        NcaSrcLnkdTriggerUnregisterWait(a2, v11);
        goto LABEL_17;
      }
      v15 = 1;
    }
    LODWORD(v11[2].Flink) = v15;
    NcaSrcLnkdTriggerRegisterForSource(a2, v11);
    HIDWORD(v11[1].Flink) = 1;
    *a6 = v11;
LABEL_17:
    v13 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_18;
  }
  v12 = 14;
  v13 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v12;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_3bebb8bd632b3e04288e9ea9721fbba3_Traceguids, 14);
    goto LABEL_17;
  }
LABEL_18:
  if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 8) != 0 )
    WPP_SF_d(v13[2], 32, WPP_3bebb8bd632b3e04288e9ea9721fbba3_Traceguids, v12);
  return v12;
}

```

## disassembly

```asm
0x18000b1e8  push    rbx
0x18000b1ea  push    rbp
0x18000b1eb  push    rsi
0x18000b1ec  push    rdi
0x18000b1ed  push    r14
0x18000b1ef  push    r15
0x18000b1f1  sub     rsp, 28h
0x18000b1f5  mov     r14, r9
0x18000b1f8  mov     rsi, r8
0x18000b1fb  mov     rbp, rdx
0x18000b1fe  mov     ebx, ecx
0x18000b200  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b207  lea     r15, WPP_GLOBAL_Control
0x18000b20e  cmp     rcx, r15
0x18000b211  jz      short loc_18000B22E
0x18000b213  test    byte ptr [rcx+1Ch], 8
0x18000b217  jz      short loc_18000B22E
0x18000b219  mov     rcx, [rcx+10h]
0x18000b21d  lea     r8, WPP_3bebb8bd632b3e04288e9ea9721fbba3_Traceguids
0x18000b224  mov     edx, 1Dh
0x18000b229  call    WPP_SF_
0x18000b22e  mov     ecx, 30h ; '0'
0x18000b233  call    NcaAlloc
0x18000b238  mov     rdi, rax
0x18000b23b  test    rax, rax
0x18000b23e  jnz     short loc_18000B278
0x18000b240  lea     ebx, [rax+0Eh]
0x18000b243  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b24a  cmp     rcx, r15
0x18000b24d  jz      loc_18000B328
0x18000b253  test    byte ptr [rcx+1Ch], 1
0x18000b257  jz      loc_18000B305
0x18000b25d  mov     rcx, [rcx+10h]
0x18000b261  lea     edx, [rax+1Eh]
0x18000b264  mov     r9d, ebx
0x18000b267  lea     r8, WPP_3bebb8bd632b3e04288e9ea9721fbba3_Traceguids
0x18000b26e  call    WPP_SF_d
0x18000b273  jmp     loc_18000B2FE
0x18000b278  mov     [rax+10h], ebx
0x18000b27b  test    rsi, rsi
0x18000b27e  jnz     short loc_18000B2D6
0x18000b280  mov     rdx, [rsp+58h+pv]; pv
0x18000b288  lea     r8, [rax+18h]
0x18000b28c  mov     rcx, r14; pfnwa
0x18000b28f  call    NcaTriggerRegisterWait
0x18000b294  mov     ebx, eax
0x18000b296  test    eax, eax
0x18000b298  jz      short loc_18000B2CF
0x18000b29a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b2a1  cmp     rcx, r15
0x18000b2a4  jz      short loc_18000B2C2
0x18000b2a6  test    byte ptr [rcx+1Ch], 1
0x18000b2aa  jz      short loc_18000B2C2
0x18000b2ac  mov     rcx, [rcx+10h]
0x18000b2b0  lea     edx, [rsi+1Fh]
0x18000b2b3  mov     r9d, eax
0x18000b2b6  lea     r8, WPP_3bebb8bd632b3e04288e9ea9721fbba3_Traceguids
0x18000b2bd  call    WPP_SF_d
0x18000b2c2  mov     rdx, rdi; struct _LIST_ENTRY *
0x18000b2c5  mov     rcx, rbp; lpCriticalSection
0x18000b2c8  call    NcaSrcLnkdTriggerUnregisterWait
0x18000b2cd  jmp     short loc_18000B2FE
0x18000b2cf  mov     eax, 1
0x18000b2d4  jmp     short loc_18000B2DE
0x18000b2d6  xor     ebx, ebx
0x18000b2d8  mov     [rax+18h], rsi
0x18000b2dc  xor     eax, eax
0x18000b2de  mov     rdx, rdi; struct _LIST_ENTRY *
0x18000b2e1  mov     [rdi+20h], eax
0x18000b2e4  mov     rcx, rbp; lpCriticalSection
0x18000b2e7  call    ?NcaSrcLnkdTriggerRegisterForSource@@YAXPEAUNCA_SYNCED_LIST_HEAD_@@PEAU_LIST_ENTRY@@@Z; NcaSrcLnkdTriggerRegisterForSource(NCA_SYNCED_LIST_HEAD_ *,_LIST_ENTRY *)
0x18000b2ec  mov     rax, [rsp+58h+arg_28]
0x18000b2f4  mov     dword ptr [rdi+14h], 1
0x18000b2fb  mov     [rax], rdi
0x18000b2fe  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b305  cmp     rcx, r15
0x18000b308  jz      short loc_18000B328
0x18000b30a  test    byte ptr [rcx+1Ch], 8
0x18000b30e  jz      short loc_18000B328
0x18000b310  mov     rcx, [rcx+10h]
0x18000b314  lea     r8, WPP_3bebb8bd632b3e04288e9ea9721fbba3_Traceguids
0x18000b31b  mov     edx, 20h ; ' '
0x18000b320  mov     r9d, ebx
0x18000b323  call    WPP_SF_d
0x18000b328  mov     eax, ebx
0x18000b32a  add     rsp, 28h
0x18000b32e  pop     r15
0x18000b330  pop     r14
0x18000b332  pop     rdi
0x18000b333  pop     rsi
0x18000b334  pop     rbp
0x18000b335  pop     rbx
0x18000b336  retn
```
