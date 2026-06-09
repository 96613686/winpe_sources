# SecSendFileOpenEvent

- ea: `0x1400275b4`
- end: `0x1400278c5`
- name: `SecSendFileOpenEvent`
- size: `785`
- prototype: `__int64 __usercall@<rax>(PFLT_CALLBACK_DATA CallbackData@<rcx>, __int64, char, char, __int64, char, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation`

## callers

- `0x140023e10`

## callees

- `0x140004fb0`
- `0x140006d3c`
- `0x14000885c`
- `0x14000888c`
- `0x140009b80`
- `0x140010347`
- `0x1400103e3`
- `0x140010473`
- `0x140011650`
- `0x1400275b4`
- `0x14002aa18`

## import_xrefs

- `ntoskrnl!PsGetThreadId` at `0x14002773a`
- `ntoskrnl!PsGetThreadId` at `0x14002773a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140027895`
- `ntoskrnl!ExFreePoolWithTag` at `0x140044608`
- `ntoskrnl!ExFreePoolWithTag` at `0x140027895`
- `ntoskrnl!ExFreePoolWithTag` at `0x140044608`

## pseudocode

```c
void __fastcall SecSendFileOpenEvent(
        PFLT_CALLBACK_DATA CallbackData,
        __int64 a2,
        char a3,
        char a4,
        __int64 a5,
        char a6,
        int a7,
        __int64 a8,
        char a9,
        __int64 a10)
{
  int InstanceContext_0; // eax
  int v13; // r13d
  struct _KTHREAD *Thread; // rbx
  int v15; // esi
  int v16; // r12d
  wchar_t *v17; // rdx
  __int64 v18; // r9
  int Information; // r10d
  wchar_t *Str; // r11
  void *Sid; // rbx
  __int64 v22; // r8
  signed __int64 v23; // rdi
  unsigned int v24; // eax
  int ThreadId; // [rsp+C8h] [rbp-70h]
  PFLT_CONTEXT Context; // [rsp+D0h] [rbp-68h] BYREF
  PVOID P; // [rsp+D8h] [rbp-60h] BYREF
  PVOID v30; // [rsp+E0h] [rbp-58h] BYREF
  _BYTE v31[4]; // [rsp+E8h] [rbp-50h] BYREF
  ULONG SessionId; // [rsp+ECh] [rbp-4Ch] BYREF

  SessionId = 0;
  P = 0;
  Context = 0;
  v30 = 0;
  v31[0] = 0;
  if ( (xmmword_14001B740 & 0x20) != 0 )
  {
    InstanceContext_0 = FltGetInstanceContext_0(*(PFLT_INSTANCE *)(a2 + 24), &Context);
    if ( InstanceContext_0 >= 0 )
    {
      v13 = (*((_DWORD *)Context + 10) >> 1) & 1;
      InstanceContext_0 = FltGetRequestorSessionId_0(CallbackData, &SessionId);
      if ( InstanceContext_0 >= 0 )
      {
        _mm_lfence();
        Thread = CallbackData->Thread;
        if ( !Thread )
          Thread = KeGetCurrentThread();
        InstanceContext_0 = SecGetEffectiveTokenUser(Thread, a5, &v30, v31, 0);
        if ( InstanceContext_0 >= 0 )
        {
          InstanceContext_0 = SecAppendUnicodeStringToUnicodeString(
                                (char *)Context + 24,
                                *(_QWORD *)(a2 + 32) + 88LL,
                                &P,
                                1953719123);
          if ( InstanceContext_0 >= 0 )
          {
            _mm_lfence();
            v15 = 0;
            if ( (unsigned int)(a7 - 2) <= 1 )
              v15 = 128;
            ThreadId = (unsigned int)PsGetThreadId(Thread);
            v16 = *(_DWORD *)(a5 + 32);
            v17 = *(wchar_t **)(a8 + 8);
            v18 = *(_QWORD *)(a5 + 48);
            Information = CallbackData->IoStatus.Information;
            Str = (wchar_t *)*((_QWORD *)P + 1);
            Sid = *(void **)v30;
            v22 = *(_QWORD *)(a5 + 40);
            v23 = _InterlockedExchangeAdd64((volatile signed __int64 *)SecData + 42, 1u);
            v24 = EventWriteOpenFile(
                    v23 + 1,
                    v16,
                    v22,
                    ThreadId,
                    Sid,
                    SessionId,
                    Str,
                    -1,
                    a3,
                    Information,
                    v18,
                    v13,
                    a6,
                    a4,
                    a7,
                    v17,
                    v15,
                    a10,
                    a9);
            SecIncrementEtwCounters(v24);
            InstanceContext_0 = 0;
          }
        }
      }
    }
    if ( InstanceContext_0 < 0 )
      SecIncrementInternalErrorCounter();
    if ( Context )
      FltReleaseContext_0(Context);
    if ( P )
      SecFreePool(P, 0x74736353u);
    if ( v30 )
    {
      if ( v31[0] )
        ExFreePoolWithTag(v30, 0);
    }
  }
}

```

## disassembly

```asm
0x1400275b4  mov     r11, rsp
0x1400275b7  push    rbx
0x1400275b8  push    rsi
0x1400275b9  push    rdi
0x1400275ba  push    r12
0x1400275bc  push    r13
0x1400275be  push    r14
0x1400275c0  push    r15
0x1400275c2  sub     rsp, 100h
0x1400275c9  mov     rax, cs:__security_cookie
0x1400275d0  xor     rax, rsp
0x1400275d3  mov     [rsp+138h+var_48], rax
0x1400275db  mov     [rsp+138h+var_94], r9w
0x1400275e4  mov     dword ptr [rsp+138h+var_90], r8d
0x1400275ec  mov     rsi, rdx
0x1400275ef  mov     rdi, rcx
0x1400275f2  mov     r12, [rsp+138h+arg_20]
0x1400275fa  mov     [rsp+138h+var_80], r12
0x140027602  mov     rax, [rsp+138h+arg_38]
0x14002760a  mov     [rsp+138h+var_88], rax
0x140027612  mov     rax, [rsp+138h+arg_48]
0x14002761a  mov     [rsp+138h+var_78], rax
0x140027622  xor     r15d, r15d
0x140027625  mov     [r11-98h], r15d
0x14002762c  mov     [r11-4Ch], r15d
0x140027630  mov     [r11-60h], r15
0x140027634  mov     [r11-68h], r15
0x140027638  mov     [r11-58h], r15
0x14002763c  mov     [r11-50h], r15b
0x140027640  mov     rax, qword ptr cs:xmmword_14001B740
0x140027647  shr     al, 5
0x14002764a  test    al, 1
0x14002764c  jz      loc_1400278A1
0x140027652  lea     rdx, [r11-68h]; Context
0x140027656  mov     rcx, [rsi+18h]; Instance
0x14002765a  call    FltGetInstanceContext_0
0x14002765f  mov     [rsp+138h+var_98], eax
0x140027666  test    eax, eax
0x140027668  js      loc_14002784A
0x14002766e  mov     rax, [rsp+138h+Context]
0x140027676  mov     r13d, [rax+28h]
0x14002767a  shr     r13d, 1
0x14002767d  and     r13d, 1
0x140027681  lea     rdx, [rsp+138h+SessionId]; SessionId
0x140027689  mov     rcx, rdi; CallbackData
0x14002768c  call    FltGetRequestorSessionId_0
0x140027691  mov     [rsp+138h+var_98], eax
0x140027698  test    eax, eax
0x14002769a  js      loc_14002784A
0x1400276a0  lfence
0x1400276a3  mov     rbx, [rdi+8]
0x1400276a7  test    rbx, rbx
0x1400276aa  jnz     short loc_1400276B5
0x1400276ac  mov     rbx, gs:188h
0x1400276b5  mov     [rsp+138h+Sid], r15; __int64
0x1400276ba  lea     r9, [rsp+138h+var_50]
0x1400276c2  lea     r8, [rsp+138h+var_58]
0x1400276ca  mov     rdx, r12
0x1400276cd  mov     rcx, rbx; Thread
0x1400276d0  call    SecGetEffectiveTokenUser
0x1400276d5  mov     [rsp+138h+var_98], eax
0x1400276dc  test    eax, eax
0x1400276de  js      loc_14002784A
0x1400276e4  mov     rdx, [rsi+20h]
0x1400276e8  add     rdx, 58h ; 'X'
0x1400276ec  mov     rcx, [rsp+138h+Context]
0x1400276f4  add     rcx, 18h
0x1400276f8  mov     r9d, 74736353h
0x1400276fe  lea     r8, [rsp+138h+P]
0x140027706  call    SecAppendUnicodeStringToUnicodeString
0x14002770b  mov     [rsp+138h+var_98], eax
0x140027712  test    eax, eax
0x140027714  js      loc_14002784A
0x14002771a  lfence
0x14002771d  mov     r14d, dword ptr [rsp+138h+arg_30]
0x140027725  lea     eax, [r14-2]
0x140027729  mov     esi, r15d
0x14002772c  mov     ecx, 80h
0x140027731  cmp     eax, 1
0x140027734  cmovbe  esi, ecx
0x140027737  mov     rcx, rbx; Thread
0x14002773a  call    cs:__imp_PsGetThreadId
0x140027741  nop     dword ptr [rax+rax+00h]
0x140027746  mov     r15, rax
0x140027749  mov     [rsp+138h+var_70], rax
0x140027751  mov     r12d, [r12+20h]
0x140027756  mov     rdx, [rsp+138h+var_88]
0x14002775e  mov     rdx, [rdx+8]
0x140027762  mov     r8, [rsp+138h+var_80]
0x14002776a  mov     r9, [r8+30h]
0x14002776e  mov     r10d, [rdi+20h]
0x140027772  mov     rcx, [rsp+138h+P]
0x14002777a  mov     r11, [rcx+8]
0x14002777e  mov     rcx, [rsp+138h+var_58]
0x140027786  mov     rbx, [rcx]
0x140027789  mov     r8, [r8+28h]; int
0x14002778d  mov     rcx, cs:SecData
0x140027794  mov     edi, 1
0x140027799  lock xadd [rcx+150h], rdi
0x1400277a2  lea     rcx, [rdi+1]; int
0x1400277a6  mov     al, [rsp+138h+arg_40]
0x1400277ad  mov     [rsp+138h+var_A8], al; char
0x1400277b4  mov     rax, [rsp+138h+var_78]
0x1400277bc  mov     [rsp+138h+var_B0], rax; __int64
0x1400277c4  mov     [rsp+138h+var_B8], esi; int
0x1400277cb  mov     [rsp+138h+var_C0], rdx; wchar_t *
0x1400277d0  mov     dword ptr [rsp+138h+var_C8], r14d; char
0x1400277d5  movzx   eax, [rsp+138h+var_94]
0x1400277dd  mov     word ptr [rsp+138h+var_D0], ax; char
0x1400277e2  mov     eax, dword ptr [rsp+138h+arg_28]
0x1400277e9  mov     dword ptr [rsp+138h+var_D8], eax; char
0x1400277ed  mov     dword ptr [rsp+138h+var_E0], r13d; char
0x1400277f2  mov     qword ptr [rsp+138h+var_E8], r9; char
0x1400277f7  mov     dword ptr [rsp+138h+var_F0], r10d; char
0x1400277fc  mov     eax, dword ptr [rsp+138h+var_90]
0x140027803  mov     dword ptr [rsp+138h+var_F8], eax; char
0x140027807  mov     dword ptr [rsp+138h+var_100], 0FFFFFFFFh; char
0x14002780f  mov     [rsp+138h+Str], r11; Str
0x140027814  mov     eax, [rsp+138h+SessionId]
0x14002781b  mov     dword ptr [rsp+138h+var_110], eax; char
0x14002781f  mov     [rsp+138h+Sid], rbx; Sid
0x140027824  mov     r9d, r15d; int
0x140027827  mov     edx, r12d; int
0x14002782a  call    EventWriteOpenFile
0x14002782f  mov     [rsp+138h+var_98], eax
0x140027836  mov     ecx, eax
0x140027838  call    SecIncrementEtwCounters
0x14002783d  xor     r15d, r15d
0x140027840  mov     eax, r15d
0x140027843  mov     [rsp+138h+var_98], eax
0x14002784a  test    eax, eax
0x14002784c  jns     short loc_140027853
0x14002784e  call    SecIncrementInternalErrorCounter
0x140027853  mov     rcx, [rsp+138h+Context]; Context
0x14002785b  test    rcx, rcx
0x14002785e  jz      short loc_140027865
0x140027860  call    FltReleaseContext_0
0x140027865  mov     rcx, [rsp+138h+P]; P
0x14002786d  test    rcx, rcx
0x140027870  jz      short loc_14002787C
0x140027872  mov     edx, 74736353h; Tag
0x140027877  call    SecFreePool
0x14002787c  mov     rcx, [rsp+138h+var_58]; P
0x140027884  test    rcx, rcx
0x140027887  jz      short loc_1400278A1
0x140027889  cmp     [rsp+138h+var_50], r15b
0x140027891  jz      short loc_1400278A1
0x140027893  xor     edx, edx; Tag
0x140027895  call    cs:__imp_ExFreePoolWithTag
0x14002789c  nop     dword ptr [rax+rax+00h]
0x1400278a1  mov     rcx, [rsp+138h+var_48]
0x1400278a9  xor     rcx, rsp; StackCookie
0x1400278ac  call    __security_check_cookie
0x1400278b1  add     rsp, 100h
0x1400278b8  pop     r15
0x1400278ba  pop     r14
0x1400278bc  pop     r13
0x1400278be  pop     r12
0x1400278c0  pop     rdi
0x1400278c1  pop     rsi
0x1400278c2  pop     rbx
0x1400278c3  retn
0x1400445ad  push    rbp
0x1400445af  sub     rsp, 0A0h
0x1400445b6  mov     rbp, rdx
0x1400445b9  cmp     dword ptr [rbp+0A0h], 0
0x1400445c0  jge     short loc_1400445C8
0x1400445c2  call    SecIncrementInternalErrorCounter
0x1400445c7  nop
0x1400445c8  mov     rcx, [rbp+0D0h]; Context
0x1400445cf  test    rcx, rcx
0x1400445d2  jz      short loc_1400445DA
0x1400445d4  call    FltReleaseContext_0
0x1400445d9  nop
0x1400445da  mov     rcx, [rbp+0D8h]; P
0x1400445e1  test    rcx, rcx
0x1400445e4  jz      short loc_1400445F1
0x1400445e6  mov     edx, 74736353h; Tag
0x1400445eb  call    SecFreePool
0x1400445f0  nop
0x1400445f1  mov     rcx, [rbp+0E0h]; P
0x1400445f8  test    rcx, rcx
0x1400445fb  jz      short loc_140044615
0x1400445fd  cmp     byte ptr [rbp+0E8h], 0
0x140044604  jz      short loc_140044615
0x140044606  xor     edx, edx; Tag
0x140044608  call    cs:__imp_ExFreePoolWithTag
0x14004460f  nop     dword ptr [rax+rax+00h]
0x140044614  nop
0x140044615  add     rsp, 0A0h
0x14004461c  pop     rbp
0x14004461d  retn
```
