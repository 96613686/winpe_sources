# FveTransform

- ea: `0x1400d2f60`
- end: `0x1400d33ad`
- name: `FveTransform`
- size: `1101`
- prototype: `__int64 __usercall@<rax>(ULONG_PTR BugCheckParameter2@<rcx>, char, int)`
- caller_count: `4`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1400793c4`
- `0x1400a3ce4`
- `0x1400a46d8`
- `0x1400e2bf8`

## callees

- `0x140008e80`
- `0x140008f04`
- `0x14002cac0`
- `0x1400d2f60`
- `0x1400d33b4`
- `0x1400d3a50`
- `0x1400d4a70`
- `0x1400e2500`

## import_xrefs

- `ntoskrnl!KeReadStateEvent` at `0x1400d3172`
- `ntoskrnl!KeReadStateEvent` at `0x1400d318c`
- `ntoskrnl!KeReadStateEvent` at `0x1400d3172`
- `ntoskrnl!KeReadStateEvent` at `0x1400d318c`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x1400d3104`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x1400d3104`
- `ntoskrnl!KeClearEvent` at `0x1400d3008`
- `ntoskrnl!KeClearEvent` at `0x1400d3066`
- `ntoskrnl!KeClearEvent` at `0x1400d3076`
- `ntoskrnl!KeClearEvent` at `0x1400d3008`
- `ntoskrnl!KeClearEvent` at `0x1400d3066`
- `ntoskrnl!KeClearEvent` at `0x1400d3076`
- `ntoskrnl!KeSetEvent` at `0x1400d32af`
- `ntoskrnl!KeSetEvent` at `0x1400d32af`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400d3399`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400d3399`
- `ntoskrnl!KeBugCheckEx` at `0x1400d3377`
- `ntoskrnl!KeBugCheckEx` at `0x1400d3377`

## pseudocode

```c
__int64 __fastcall FveTransform(__int64 *BugCheckParameter2, int a2, int a3, char a4, char a5, unsigned int a6)
{
  __int64 v10; // rax
  unsigned int *v11; // r13
  __int64 v12; // rax
  char v13; // r15
  int v14; // r12d
  __int64 i; // rsi
  __int64 v16; // rdi
  char v17; // al
  PVOID *__attribute__((__org_arrdim(0,0))) *v18; // r12
  PVOID *__attribute__((__org_arrdim(0,0))) *j; // r14
  __int64 v20; // rbp
  __int64 v21; // r15
  unsigned int v22; // edi
  __int64 v24; // rsi
  __int64 v25; // rdi
  __int64 v26; // rbp
  char v27; // al
  struct _KEVENT *v28; // rcx
  int v29; // edx
  int v30; // r9d
  bool v31; // zf
  int v32; // r8d
  ULONG_PTR v33; // rax
  __int64 WaitMode; // [rsp+20h] [rbp-88h]
  __int64 v35; // [rsp+B0h] [rbp+8h]
  int v36; // [rsp+C0h] [rbp+18h] BYREF
  char v37; // [rsp+C8h] [rbp+20h] BYREF

  v37 = a4;
  v36 = a3;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_c6388269e3fb3c909e30f9fcb6861b16_Traceguids);
  }
  v10 = BugCheckParameter2[1];
  v35 = BugCheckParameter2[7];
  v11 = *(unsigned int **)(v10 + 8);
  if ( a5 && !*(_DWORD *)(v10 + 1324) )
  {
    v12 = v11[221];
    if ( (__int64 (__fastcall *)(int, int, int, int, int, PUCHAR, PUCHAR, __int64))BugCheckParameter2[16] == FveFilteredEncrypt )
    {
      if ( v11[v12 + 343] != -1 )
        goto LABEL_6;
    }
    else if ( v11[v12 + 346] != -1 )
    {
LABEL_6:
      v13 = 1;
      goto LABEL_9;
    }
  }
  v13 = 0;
LABEL_9:
  a5 = v13;
  KeClearEvent((PRKEVENT)(BugCheckParameter2 + 2));
  v14 = a6;
  *((_DWORD *)BugCheckParameter2 + 19) = 0;
  *((_DWORD *)BugCheckParameter2 + 20) = 0;
  *((_DWORD *)BugCheckParameter2 + 103) = v14;
  *((_DWORD *)BugCheckParameter2 + 100) = a2;
  *((_DWORD *)BugCheckParameter2 + 101) = a3;
  *((_BYTE *)BugCheckParameter2 + 408) = a4;
  _InterlockedIncrement((volatile signed __int32 *)BugCheckParameter2 + 20);
  for ( i = 0; (unsigned int)i < *((_DWORD *)BugCheckParameter2 + 18); i = (unsigned int)(i + 1) )
  {
    v16 = *BugCheckParameter2 + 80 * i;
    *(_DWORD *)(*(_QWORD *)(v16 + 8) + 48LL) = v14;
    KeClearEvent((PRKEVENT)(v16 + 16));
    KeClearEvent((PRKEVENT)(v16 + 40));
    *(_BYTE *)(v16 + 64) = 0;
    if ( (unsigned int)i >= *((_DWORD *)BugCheckParameter2 + 18) - 1
      || (v17 = 0, (unsigned int)(*((_DWORD *)BugCheckParameter2 + 22) * (i + 1)) >= *((_DWORD *)BugCheckParameter2 + 23)) )
    {
      v17 = 1;
    }
    *(_BYTE *)(v16 + 65) = v17;
    _InterlockedIncrement((volatile signed __int32 *)BugCheckParameter2 + 20);
    if ( v13 )
    {
      FveCryptoWorkQueue(v11, *(_QWORD *)(v16 + 8), 0, 0);
    }
    else
    {
      if ( *(_BYTE *)(v16 + 65)
        || (v27 = FvepQueueWorkItem(v11, *(_QWORD *)(v16 + 8), v36, v37, (__int64)FveTransformWork, v16, 0, v14, 1),
            v28 = (struct _KEVENT *)(v16 + 16),
            !v27) )
      {
        v28 = (struct _KEVENT *)(v16 + 40);
      }
      KeSetEvent(v28, 0, 0);
    }
    if ( *(_BYTE *)(v16 + 65) )
      break;
  }
  v18 = (PVOID *__attribute__((__org_arrdim(0,0))) *)(BugCheckParameter2 + 5);
  for ( j = (PVOID *__attribute__((__org_arrdim(0,0))) *)(BugCheckParameter2 + 5);
        ;
        KeWaitForMultipleObjects(v20, *j, WaitAny, Executive, 0, 0, 0, (PKWAIT_BLOCK)BugCheckParameter2[6]) )
  {
    v20 = 0;
    v21 = 0;
    while ( (unsigned int)v21 < *((_DWORD *)BugCheckParameter2 + 18) )
    {
      v24 = *BugCheckParameter2;
      v25 = 80 * v21;
      if ( !KeReadStateEvent((PRKEVENT)(80 * v21 + *BugCheckParameter2 + 16)) )
      {
        if ( KeReadStateEvent((PRKEVENT)(v25 + v24 + 40)) )
        {
          if ( !*(_BYTE *)(v25 + v24 + 64) )
          {
            FveTransformWork(v11, *(_QWORD *)(v25 + v24 + 8));
            v31 = a5 == 0;
            *(_BYTE *)(v25 + v24 + 64) = 1;
            if ( !v31 )
            {
              LOBYTE(v30) = *(_BYTE *)(v25 + v24 + 72);
              v32 = *(_DWORD *)(v25 + v24 + 68);
              LOBYTE(v29) = BugCheckParameter2[16] == (_QWORD)FveFilteredEncrypt;
              v36 = 0;
              WaitMode = *(_QWORD *)(v25 + v24 + 8);
              v37 = 0;
              v33 = FveGlobalCryptoThrottleComplete(
                      (_DWORD)v11,
                      v29,
                      v32,
                      v30,
                      WaitMode,
                      0,
                      (__int64)&v36,
                      (__int64)&v37);
              if ( v33 )
                KeBugCheckEx(0x120u, 0xCu, (ULONG_PTR)BugCheckParameter2, 0, v33);
            }
          }
        }
        else
        {
          (*j)[v20] = (PVOID)(v25 + v24 + 16);
          v26 = (unsigned int)(v20 + 1);
          (*j)[v26] = (PVOID)(v25 + v24 + 40);
          v20 = (unsigned int)(v26 + 1);
        }
        v18 = (PVOID *__attribute__((__org_arrdim(0,0))) *)(BugCheckParameter2 + 5);
      }
      if ( *(_BYTE *)(v25 + v24 + 65) )
        break;
      v21 = (unsigned int)(v21 + 1);
      j = v18;
    }
    if ( !(_DWORD)v20 )
      break;
  }
  v22 = 259;
  FveTransformWorkComplete(BugCheckParameter2, a6);
  if ( !v35 )
  {
    KeWaitForSingleObject(BugCheckParameter2 + 2, Executive, 0, 0, 0);
    v22 = *((_DWORD *)BugCheckParameter2 + 19);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_c6388269e3fb3c909e30f9fcb6861b16_Traceguids, v22);
  }
  return v22;
}

```

## disassembly

```asm
0x1400d2f60  mov     [rsp+arg_18], r9b
0x1400d2f65  mov     [rsp+arg_10], r8d
0x1400d2f6a  mov     [rsp+arg_8], edx
0x1400d2f6e  push    rbx
0x1400d2f6f  push    rbp
0x1400d2f70  push    rsi
0x1400d2f71  push    rdi
0x1400d2f72  push    r12
0x1400d2f74  push    r13
0x1400d2f76  push    r14
0x1400d2f78  push    r15
0x1400d2f7a  sub     rsp, 68h
0x1400d2f7e  mov     dil, r9b
0x1400d2f81  mov     esi, r8d
0x1400d2f84  mov     ebp, edx
0x1400d2f86  mov     rbx, rcx
0x1400d2f89  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d2f90  lea     rax, WPP_GLOBAL_Control
0x1400d2f97  cmp     rcx, rax
0x1400d2f9a  jnz     loc_1400D31EA
0x1400d2fa0  cmp     [rsp+0A8h+arg_20], 0
0x1400d2fa8  mov     rcx, [rbx+38h]
0x1400d2fac  mov     rax, [rbx+8]
0x1400d2fb0  mov     [rsp+0A8h+arg_0], rcx
0x1400d2fb8  lea     rcx, FveFilteredEncrypt
0x1400d2fbf  mov     r13, [rax+8]
0x1400d2fc3  jz      short loc_1400D2FF9
0x1400d2fc5  cmp     dword ptr [rax+52Ch], 0
0x1400d2fcc  jnz     short loc_1400D2FF9
0x1400d2fce  mov     eax, [r13+374h]
0x1400d2fd5  cmp     [rbx+80h], rcx
0x1400d2fdc  jz      short loc_1400D2FEE
0x1400d2fde  cmp     dword ptr [r13+rax*4+568h], 0FFFFFFFFh
0x1400d2fe7  jz      short loc_1400D2FF9
0x1400d2fe9  mov     r15b, 1
0x1400d2fec  jmp     short loc_1400D2FFC
0x1400d2fee  cmp     dword ptr [r13+rax*4+55Ch], 0FFFFFFFFh
0x1400d2ff7  jnz     short loc_1400D2FE9
0x1400d2ff9  xor     r15b, r15b
0x1400d2ffc  lea     rcx, [rbx+10h]; Event
0x1400d3000  mov     [rsp+0A8h+arg_20], r15b
0x1400d3008  call    cs:__imp_KeClearEvent
0x1400d300f  nop     dword ptr [rax+rax+00h]
0x1400d3014  mov     r12d, [rsp+0A8h+arg_28]
0x1400d301c  mov     dword ptr [rbx+4Ch], 0
0x1400d3023  mov     dword ptr [rbx+50h], 0
0x1400d302a  mov     [rbx+19Ch], r12d
0x1400d3031  mov     [rbx+190h], ebp
0x1400d3037  mov     [rbx+194h], esi
0x1400d303d  mov     [rbx+198h], dil
0x1400d3044  lock inc dword ptr [rbx+50h]
0x1400d3048  xor     esi, esi
0x1400d304a  cmp     [rbx+48h], esi
0x1400d304d  jbe     short loc_1400D30C2
0x1400d304f  lea     rdi, [rsi+rsi*4]
0x1400d3053  shl     rdi, 4
0x1400d3057  add     rdi, [rbx]
0x1400d305a  mov     rax, [rdi+8]
0x1400d305e  lea     rcx, [rdi+10h]; Event
0x1400d3062  mov     [rax+30h], r12d
0x1400d3066  call    cs:__imp_KeClearEvent
0x1400d306d  nop     dword ptr [rax+rax+00h]
0x1400d3072  lea     rcx, [rdi+28h]; Event
0x1400d3076  call    cs:__imp_KeClearEvent
0x1400d307d  nop     dword ptr [rax+rax+00h]
0x1400d3082  xor     ecx, ecx
0x1400d3084  mov     [rdi+40h], cl
0x1400d3087  mov     eax, [rbx+48h]
0x1400d308a  dec     eax
0x1400d308c  cmp     esi, eax
0x1400d308e  jb      loc_1400D31D3
0x1400d3094  mov     al, 1
0x1400d3096  mov     [rdi+41h], al
0x1400d3099  lock inc dword ptr [rbx+50h]
0x1400d309d  test    r15b, r15b
0x1400d30a0  jz      loc_1400D324C
0x1400d30a6  mov     rdx, [rdi+8]
0x1400d30aa  xor     r9d, r9d
0x1400d30ad  xor     r8d, r8d
0x1400d30b0  mov     rcx, r13
0x1400d30b3  call    FveCryptoWorkQueue
0x1400d30b8  cmp     byte ptr [rdi+41h], 0
0x1400d30bc  jz      loc_1400D32C0
0x1400d30c2  lea     r12, [rbx+28h]
0x1400d30c6  mov     r14, r12
0x1400d30c9  xor     ebp, ebp
0x1400d30cb  xor     r15d, r15d
0x1400d30ce  cmp     r15d, [rbx+48h]
0x1400d30d2  jb      loc_1400D3160
0x1400d30d8  test    ebp, ebp
0x1400d30da  jz      short loc_1400D3112
0x1400d30dc  mov     rax, [rbx+30h]
0x1400d30e0  xor     r9d, r9d; WaitReason
0x1400d30e3  mov     rdx, [r14]; Object
0x1400d30e6  mov     ecx, ebp; Count
0x1400d30e8  mov     [rsp+0A8h+WaitBlockArray], rax; WaitBlockArray
0x1400d30ed  mov     [rsp+0A8h+Timeout], 0; Timeout
0x1400d30f6  lea     r8d, [r9+1]; WaitType
0x1400d30fa  mov     [rsp+0A8h+Alertable], 0; Alertable
0x1400d30ff  mov     [rsp+0A8h+WaitMode], 0; WaitMode
0x1400d3104  call    cs:__imp_KeWaitForMultipleObjects
0x1400d310b  nop     dword ptr [rax+rax+00h]
0x1400d3110  jmp     short loc_1400D30C9
0x1400d3112  mov     edx, [rsp+0A8h+arg_28]
0x1400d3119  mov     rcx, rbx
0x1400d311c  mov     edi, 103h
0x1400d3121  call    FveTransformWorkComplete
0x1400d3126  cmp     [rsp+0A8h+arg_0], 0
0x1400d312f  jz      loc_1400D3384
0x1400d3135  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d313c  lea     rax, WPP_GLOBAL_Control
0x1400d3143  cmp     rcx, rax
0x1400d3146  jnz     loc_1400D3219
0x1400d314c  mov     eax, edi
0x1400d314e  add     rsp, 68h
0x1400d3152  pop     r15
0x1400d3154  pop     r14
0x1400d3156  pop     r13
0x1400d3158  pop     r12
0x1400d315a  pop     rdi
0x1400d315b  pop     rsi
0x1400d315c  pop     rbp
0x1400d315d  pop     rbx
0x1400d315e  retn
0x1400d3160  mov     rsi, [rbx]
0x1400d3163  lea     rdi, [r15+r15*4]
0x1400d3167  shl     rdi, 4
0x1400d316b  lea     rcx, [rsi+10h]
0x1400d316f  add     rcx, rdi; Event
0x1400d3172  call    cs:__imp_KeReadStateEvent
0x1400d3179  nop     dword ptr [rax+rax+00h]
0x1400d317e  test    eax, eax
0x1400d3180  jnz     short loc_1400D31BD
0x1400d3182  lea     r12, [rsi+28h]
0x1400d3186  add     r12, rdi
0x1400d3189  mov     rcx, r12; Event
0x1400d318c  call    cs:__imp_KeReadStateEvent
0x1400d3193  nop     dword ptr [rax+rax+00h]
0x1400d3198  test    eax, eax
0x1400d319a  jnz     loc_1400D32D0
0x1400d31a0  mov     rax, [r14]
0x1400d31a3  lea     rdx, [rsi+10h]
0x1400d31a7  add     rdx, rdi
0x1400d31aa  mov     [rax+rbp*8], rdx
0x1400d31ae  inc     ebp
0x1400d31b0  mov     rax, [r14]
0x1400d31b3  mov     [rax+rbp*8], r12
0x1400d31b7  inc     ebp
0x1400d31b9  lea     r12, [rbx+28h]
0x1400d31bd  cmp     byte ptr [rdi+rsi+41h], 0
0x1400d31c2  jnz     loc_1400D30D8
0x1400d31c8  inc     r15d
0x1400d31cb  mov     r14, r12
0x1400d31ce  jmp     loc_1400D30CE
0x1400d31d3  lea     eax, [rsi+1]
0x1400d31d6  imul    eax, [rbx+58h]
0x1400d31da  cmp     eax, [rbx+5Ch]
0x1400d31dd  mov     al, cl
0x1400d31df  jb      loc_1400D3096
0x1400d31e5  jmp     loc_1400D3094
0x1400d31ea  mov     eax, [rcx+2Ch]
0x1400d31ed  test    al, 2
0x1400d31ef  jz      loc_1400D2FA0
0x1400d31f5  cmp     byte ptr [rcx+29h], 5
0x1400d31f9  jb      loc_1400D2FA0
0x1400d31ff  mov     rcx, [rcx+18h]
0x1400d3203  lea     r8, WPP_c6388269e3fb3c909e30f9fcb6861b16_Traceguids
0x1400d320a  mov     edx, 10h
0x1400d320f  call    WPP_SF_
0x1400d3214  jmp     loc_1400D2FA0
0x1400d3219  mov     edx, [rcx+2Ch]
0x1400d321c  test    dl, 2
0x1400d321f  jz      loc_1400D314C
0x1400d3225  cmp     byte ptr [rcx+29h], 5
0x1400d3229  jb      loc_1400D314C
0x1400d322f  mov     rcx, [rcx+18h]
0x1400d3233  lea     r8, WPP_c6388269e3fb3c909e30f9fcb6861b16_Traceguids
0x1400d323a  mov     edx, 11h
0x1400d323f  mov     r9d, edi
0x1400d3242  call    WPP_SF_d
0x1400d3247  jmp     loc_1400D314C
0x1400d324c  cmp     [rdi+41h], cl
0x1400d324f  jnz     short loc_1400D32A6
0x1400d3251  mov     r9d, [rsp+0A8h+arg_8]
0x1400d3259  lea     rax, FveTransformWork
0x1400d3260  mov     rdx, [rdi+8]; BugCheckParameter2
0x1400d3264  xor     r8d, r8d
0x1400d3267  mov     [rsp+0A8h+var_58], 1; char
0x1400d326c  mov     [rsp+0A8h+var_60], r12d; int
0x1400d3271  mov     [rsp+0A8h+var_68], rcx; __int64
0x1400d3276  mov     rcx, r13; Context
0x1400d3279  mov     [rsp+0A8h+WaitBlockArray], rdi; __int64
0x1400d327e  mov     [rsp+0A8h+Timeout], rax; __int64
0x1400d3283  mov     al, [rsp+0A8h+arg_18]
0x1400d328a  mov     [rsp+0A8h+Alertable], al; char
0x1400d328e  mov     eax, [rsp+0A8h+arg_10]
0x1400d3295  mov     dword ptr [rsp+0A8h+WaitMode], eax; int
0x1400d3299  call    FvepQueueWorkItem
0x1400d329e  lea     rcx, [rdi+10h]
0x1400d32a2  test    al, al
0x1400d32a4  jnz     short loc_1400D32AA
0x1400d32a6  lea     rcx, [rdi+28h]; Event
0x1400d32aa  xor     r8d, r8d; Wait
0x1400d32ad  xor     edx, edx; Increment
0x1400d32af  call    cs:__imp_KeSetEvent
0x1400d32b6  nop     dword ptr [rax+rax+00h]
0x1400d32bb  jmp     loc_1400D30B8
0x1400d32c0  inc     esi
0x1400d32c2  cmp     esi, [rbx+48h]
0x1400d32c5  jb      loc_1400D304F
0x1400d32cb  jmp     loc_1400D30C2
0x1400d32d0  cmp     byte ptr [rdi+rsi+40h], 0
0x1400d32d5  jnz     loc_1400D31B9
0x1400d32db  mov     rdx, [rdi+rsi+8]
0x1400d32e0  mov     rcx, r13
0x1400d32e3  call    FveTransformWork
0x1400d32e8  cmp     [rsp+0A8h+arg_20], 0
0x1400d32f0  mov     byte ptr [rdi+rsi+40h], 1
0x1400d32f5  jz      loc_1400D31B9
0x1400d32fb  mov     r9b, [rdi+rsi+48h]
0x1400d3300  lea     rax, FveFilteredEncrypt
0x1400d3307  cmp     [rbx+80h], rax
0x1400d330e  mov     rcx, r13
0x1400d3311  mov     r8d, [rdi+rsi+44h]
0x1400d3316  lea     rax, [rsp+0A8h+arg_18]
0x1400d331e  mov     [rsp+0A8h+WaitBlockArray], rax
0x1400d3323  setz    dl
0x1400d3326  lea     rax, [rsp+0A8h+arg_10]
0x1400d332e  mov     [rsp+0A8h+arg_10], 0
0x1400d3339  mov     [rsp+0A8h+Timeout], rax
0x1400d333e  mov     rax, [rdi+rsi+8]
0x1400d3343  mov     [rsp+0A8h+Alertable], 0
0x1400d3348  mov     qword ptr [rsp+0A8h+WaitMode], rax
0x1400d334d  mov     [rsp+0A8h+arg_18], 0
0x1400d3355  call    FveGlobalCryptoThrottleComplete
0x1400d335a  test    rax, rax
0x1400d335d  jz      loc_1400D31B9
0x1400d3363  xor     r9d, r9d; BugCheckParameter3
0x1400d3366  mov     qword ptr [rsp+0A8h+WaitMode], rax; BugCheckParameter4
0x1400d336b  mov     r8, rbx; BugCheckParameter2
0x1400d336e  mov     ecx, 120h; BugCheckCode
0x1400d3373  lea     edx, [r9+0Ch]; BugCheckParameter1
0x1400d3377  call    cs:__imp_KeBugCheckEx
0x1400d3384  xor     r9d, r9d; Alertable
0x1400d3387  mov     qword ptr [rsp+0A8h+WaitMode], 0; Timeout
0x1400d3390  xor     r8d, r8d; WaitMode
0x1400d3393  lea     rcx, [rbx+10h]; Object
0x1400d3397  xor     edx, edx; WaitReason
0x1400d3399  call    cs:__imp_KeWaitForSingleObject
0x1400d33a0  nop     dword ptr [rax+rax+00h]
0x1400d33a5  mov     edi, [rbx+4Ch]
0x1400d33a8  jmp     loc_1400D3135
```
