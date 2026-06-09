# RxUpdateCondition

- ea: `0x14005c450`
- end: `0x14005c5dc`
- name: `RxUpdateCondition`
- size: `396`
- prototype: `void __stdcall(RX_BLOCK_CONDITION NewConditionValue, PRX_BLOCK_CONDITION Condition, PLIST_ENTRY TransitionWaitList)`
- caller_count: `17`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x140010760`
- `0x140010e40`
- `0x14004dff0`
- `0x14004f55c`
- `0x14004fef0`
- `0x140050414`
- `0x140050910`
- `0x140050d38`
- `0x14005a850`
- `0x140060560`
- `0x140061ee0`
- `0x14006c310`
- `0x14006d920`
- `0x140076760`
- `0x140077c50`
- `0x1400780a0`
- `0x14007a310`

## callees

- `0x140007ca0`
- `0x140022b44`
- `0x140025d00`
- `0x14005c450`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14005c58f`
- `ntoskrnl!KeSetEvent` at `0x14005c58f`
- `ntoskrnl!KeReleaseMutex` at `0x14005c5c4`
- `ntoskrnl!KeReleaseMutex` at `0x14005c5c4`
- `ntoskrnl!KeWaitForSingleObject` at `0x14005c47d`
- `ntoskrnl!KeWaitForSingleObject` at `0x14005c47d`

## pseudocode

```c
void __stdcall RxUpdateCondition(
        RX_BLOCK_CONDITION NewConditionValue,
        PRX_BLOCK_CONDITION Condition,
        PLIST_ENTRY TransitionWaitList)
{
  _DWORD *v3; // r9
  _DWORD *v4; // rdi
  int v6; // ebp
  __int64 v8; // rdx
  __int64 v9; // r8
  _QWORD *v10; // rbx
  __int64 v11; // rax
  _QWORD *v12; // rcx
  _QWORD *v13; // rbx
  int v14; // eax
  __int64 (__fastcall *v15)(_QWORD *); // rax
  int v16; // ecx
  _QWORD **v17; // [rsp+80h] [rbp+28h]
  __int16 v18; // [rsp+88h] [rbp+30h]

  v4 = v3;
  v6 = (int)Condition;
  KeWaitForSingleObject(&RxSerializationMutex, Executive, 0, 0, 0);
  if ( LODWORD(TransitionWaitList->Flink) != NewConditionValue && v4 )
    *v4 = v6;
  LODWORD(TransitionWaitList->Flink) = NewConditionValue;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_DDq(WPP_GLOBAL_Control->AttachedDevice, v8, v9, (unsigned int)NewConditionValue, v6, v17);
  }
  while ( 1 )
  {
    v10 = *v17;
    if ( *v17 == v17 )
      break;
    v11 = *v10;
    if ( *(_QWORD **)(*v10 + 8LL) != v10 || (v12 = (_QWORD *)v10[1], (_QWORD *)*v12 != v10) )
      __fastfail(3u);
    *v12 = v11;
    *(_QWORD *)(v11 + 8) = v12;
    v10[1] = v10;
    *v10 = v10;
    v13 = v10 - 18;
    if ( !v13 )
      break;
    v14 = 0;
    *((_DWORD *)v13 + 44) = v6;
    _InterlockedAnd((volatile signed __int32 *)v13 + 32, 0xFFFFFFFB);
    if ( *((int *)v13 + 44) < 0 && v18 == -5358 )
    {
      v15 = *(__int64 (__fastcall **)(_QWORD *))(*(_QWORD *)(v13[10] + 352LL) + 528LL);
      if ( v15 )
        v14 = v15(v13);
      else
        v14 = -1073741822;
    }
    v16 = *((_DWORD *)v13 + 30);
    if ( (v16 & 0x4000) != 0 )
    {
      *((_DWORD *)v13 + 30) = v16 & 0xFFFFBFFF;
      RxFsdPostRequest((PRX_CONTEXT)v13);
    }
    else
    {
      if ( v14 == -1069481983 )
        *((_DWORD *)v13 + 44) = -1069481983;
      *((_DWORD *)v13 + 30) = v16 & 0xFFEFFFFF;
      KeSetEvent((PRKEVENT)v13 + 16, 0, 0);
    }
  }
  KeReleaseMutex(&RxSerializationMutex, 0);
}

```

## disassembly

```asm
0x14005c450  push    rbx
0x14005c452  push    rbp
0x14005c453  push    rsi
0x14005c454  push    rdi
0x14005c455  push    r14
0x14005c457  sub     rsp, 30h
0x14005c45b  mov     rdi, r9
0x14005c45e  mov     [rsp+58h+Timeout], 0; Timeout
0x14005c467  mov     rsi, r8
0x14005c46a  mov     ebp, edx
0x14005c46c  mov     ebx, ecx
0x14005c46e  xor     r9d, r9d; Alertable
0x14005c471  xor     r8d, r8d; WaitMode
0x14005c474  lea     rcx, RxSerializationMutex; Object
0x14005c47b  xor     edx, edx; WaitReason
0x14005c47d  call    cs:__imp_KeWaitForSingleObject
0x14005c484  nop     dword ptr [rax+rax+00h]
0x14005c489  cmp     [rsi], ebx
0x14005c48b  jz      short loc_14005C494
0x14005c48d  test    rdi, rdi
0x14005c490  jz      short loc_14005C494
0x14005c492  mov     [rdi], ebp
0x14005c494  mov     [rsi], ebx
0x14005c496  mov     rcx, cs:WPP_GLOBAL_Control
0x14005c49d  lea     rax, WPP_GLOBAL_Control
0x14005c4a4  mov     rdi, [rsp+58h+arg_20]
0x14005c4ac  cmp     rcx, rax
0x14005c4af  jz      short loc_14005C4D3
0x14005c4b1  mov     eax, [rcx+2Ch]
0x14005c4b4  test    al, 2
0x14005c4b6  jz      short loc_14005C4D3
0x14005c4b8  cmp     byte ptr [rcx+29h], 4
0x14005c4bc  jb      short loc_14005C4D3
0x14005c4be  mov     rcx, [rcx+18h]
0x14005c4c2  mov     r9d, ebx
0x14005c4c5  mov     [rsp+58h+var_30], rdi
0x14005c4ca  mov     dword ptr [rsp+58h+Timeout], ebp
0x14005c4ce  call    WPP_SF_DDq
0x14005c4d3  movzx   esi, [rsp+58h+arg_28]
0x14005c4db  mov     r14d, 0EB12h
0x14005c4e1  mov     rbx, [rdi]
0x14005c4e4  cmp     rbx, rdi
0x14005c4e7  jz      loc_14005C5BB
0x14005c4ed  mov     rax, [rbx]
0x14005c4f0  cmp     [rax+8], rbx
0x14005c4f4  jnz     loc_14005C5B4
0x14005c4fa  mov     rcx, [rbx+8]
0x14005c4fe  cmp     [rcx], rbx
0x14005c501  jnz     loc_14005C5B4
0x14005c507  mov     [rcx], rax
0x14005c50a  mov     [rax+8], rcx
0x14005c50e  mov     [rbx+8], rbx
0x14005c512  mov     [rbx], rbx
0x14005c515  add     rbx, 0FFFFFFFFFFFFFF70h
0x14005c51c  jz      loc_14005C5BB
0x14005c522  xor     eax, eax
0x14005c524  mov     [rbx+0B0h], ebp
0x14005c52a  lock and dword ptr [rbx+80h], 0FFFFFFFBh
0x14005c532  cmp     [rbx+0B0h], eax
0x14005c538  jge     short loc_14005C566
0x14005c53a  cmp     si, r14w
0x14005c53e  jnz     short loc_14005C566
0x14005c540  mov     rax, [rbx+50h]
0x14005c544  mov     rcx, [rax+160h]
0x14005c54b  mov     rax, [rcx+210h]
0x14005c552  test    rax, rax
0x14005c555  jnz     short loc_14005C55E
0x14005c557  mov     eax, 0C0000002h
0x14005c55c  jmp     short loc_14005C566
0x14005c55e  mov     rcx, rbx
0x14005c561  call    _guard_dispatch_icall
0x14005c566  mov     ecx, [rbx+78h]
0x14005c569  bt      ecx, 0Eh
0x14005c56d  jb      short loc_14005C5A0
0x14005c56f  cmp     eax, 0C0410001h
0x14005c574  jnz     short loc_14005C57C
0x14005c576  mov     [rbx+0B0h], eax
0x14005c57c  btr     ecx, 14h
0x14005c580  xor     r8d, r8d; Wait
0x14005c583  mov     [rbx+78h], ecx
0x14005c586  xor     edx, edx; Increment
0x14005c588  lea     rcx, [rbx+180h]; Event
0x14005c58f  call    cs:__imp_KeSetEvent
0x14005c596  nop     dword ptr [rax+rax+00h]
0x14005c59b  jmp     loc_14005C4E1
0x14005c5a0  btr     ecx, 0Eh
0x14005c5a4  mov     [rbx+78h], ecx
0x14005c5a7  mov     rcx, rbx; RxContext
0x14005c5aa  call    RxFsdPostRequest
0x14005c5af  jmp     loc_14005C4E1
0x14005c5b4  mov     ecx, 3
0x14005c5b9  int     29h; Win8: RtlFailFast(ecx)
0x14005c5bb  xor     edx, edx; Wait
0x14005c5bd  lea     rcx, RxSerializationMutex; Mutex
0x14005c5c4  call    cs:__imp_KeReleaseMutex
0x14005c5cb  nop     dword ptr [rax+rax+00h]
0x14005c5d0  add     rsp, 30h
0x14005c5d4  pop     r14
0x14005c5d6  pop     rdi
0x14005c5d7  pop     rsi
0x14005c5d8  pop     rbp
0x14005c5d9  pop     rbx
0x14005c5da  retn
```
