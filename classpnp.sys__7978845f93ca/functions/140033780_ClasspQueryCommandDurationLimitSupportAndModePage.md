# ClasspQueryCommandDurationLimitSupportAndModePage

- ea: `0x140033780`
- end: `0x14003391e`
- name: `ClasspQueryCommandDurationLimitSupportAndModePage`
- size: `414`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1400316d4`

## callees

- `0x14000f3e0`
- `0x14002ec78`
- `0x140030fac`
- `0x140033780`
- `0x14003ba10`
- `0x14003e430`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400337cb`
- `ntoskrnl!ExAllocatePool2` at `0x1400337cb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400338e9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400338e9`

## pseudocode

```c
__int64 __fastcall ClasspQueryCommandDurationLimitSupportAndModePage(__int64 a1, char a2)
{
  char v4; // r15
  char v5; // r14
  int v6; // ecx
  _DWORD *Pool2; // rbx
  int v8; // r8d
  int v9; // r9d
  int v10; // edi
  __int64 v11; // rdx
  _WORD *DurationLimitCommandInfo; // rax
  __int16 v13; // dx
  int v15; // [rsp+28h] [rbp-50h]
  int BufferAddress; // [rsp+40h] [rbp-38h] BYREF
  char v17; // [rsp+44h] [rbp-34h]

  BufferAddress = 0;
  v17 = 0;
  v4 = 0;
  v5 = 0;
  Pool2 = (_DWORD *)ExAllocatePool2(64, 184, 1918067539);
  if ( !Pool2 )
  {
    v10 = -1073741670;
    goto LABEL_9;
  }
  if ( *(_BYTE *)(*(_QWORD *)(a1 + 528) + 30LL) == 1 )
  {
    v10 = InitializeStorageRequestBlock((__int64)Pool2);
    if ( v10 < 0 )
      goto LABEL_9;
    Pool2[5] = 0;
  }
  else
  {
    *(_WORD *)Pool2 = 88;
    *((_BYTE *)Pool2 + 2) = 0;
  }
  v10 = ClasspDeviceIssueReportSupportedOperationCodesCommand(a1, (int)Pool2, v8, v9, a2, v15, &BufferAddress);
  if ( v10 >= 0 )
  {
    LOBYTE(v11) = a2;
    DurationLimitCommandInfo = (_WORD *)ClasspGetDurationLimitCommandInfo(a1, v11);
    v13 = *DurationLimitCommandInfo & 0xFFF7 | (8 * (BufferAddress & 1));
    *DurationLimitCommandInfo = v13;
    v4 = BufferAddress & 1;
    v6 = (BYTE1(BufferAddress) >> 3) & 3;
    LOWORD(v6) = v13 & 0xFFCF | (16 * v6);
    *DurationLimitCommandInfo = v6;
    v5 = (BYTE1(BufferAddress) >> 3) & 3;
    LOWORD(v6) = v6 | 1;
    *DurationLimitCommandInfo = v6;
  }
LABEL_9:
  if ( ClassPnPETWEnabled )
  {
    LOBYTE(v9) = a2;
    ClasspQueryCDLSupportAndModePageEvent(v6, *(_QWORD *)(a1 + 8), v10, v9, v4, v5);
  }
  if ( Pool2 )
    ExFreePoolWithTag(Pool2, 0);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140033780  mov     [rsp+arg_10], rbx
0x140033785  mov     [rsp+arg_18], rbp
0x14003378a  push    rsi
0x14003378b  push    rdi
0x14003378c  push    r13
0x14003378e  push    r14
0x140033790  push    r15
0x140033792  sub     rsp, 50h
0x140033796  mov     rax, cs:__security_cookie
0x14003379d  xor     rax, rsp
0x1400337a0  mov     [rsp+78h+var_30], rax
0x1400337a5  xor     eax, eax
0x1400337a7  mov     bpl, dl
0x1400337aa  mov     rsi, rcx
0x1400337ad  mov     [rsp+78h+var_38], eax
0x1400337b1  mov     edi, 0B8h
0x1400337b6  mov     [rsp+78h+var_34], al
0x1400337ba  mov     r8d, 72536353h
0x1400337c0  mov     edx, edi
0x1400337c2  lea     ecx, [rax+40h]
0x1400337c5  xor     r15b, r15b
0x1400337c8  xor     r14b, r14b
0x1400337cb  call    cs:__imp_ExAllocatePool2
0x1400337d2  nop     dword ptr [rax+rax+00h]
0x1400337d7  mov     rbx, rax
0x1400337da  test    rax, rax
0x1400337dd  jnz     short loc_1400337E9
0x1400337df  mov     edi, 0C000009Ah
0x1400337e4  jmp     loc_1400338BD
0x1400337e9  mov     rax, [rsi+210h]
0x1400337f0  mov     r13d, 1
0x1400337f6  cmp     [rax+1Eh], r13b
0x1400337fa  jnz     short loc_14003382A
0x1400337fc  xor     eax, eax
0x1400337fe  mov     dword ptr [rsp+78h+var_58], 40h ; '@'
0x140033806  movzx   edx, ax
0x140033809  mov     r9d, r13d
0x14003380c  mov     r8d, edi
0x14003380f  mov     rcx, rbx
0x140033812  call    InitializeStorageRequestBlock
0x140033817  mov     edi, eax
0x140033819  test    eax, eax
0x14003381b  js      loc_1400338BD
0x140033821  mov     dword ptr [rbx+14h], 0
0x140033828  jmp     short loc_140033833
0x14003382a  mov     word ptr [rbx], 58h ; 'X'
0x14003382f  mov     [rbx+2], r14b
0x140033833  lea     rax, [rsp+78h+var_38]
0x140033838  mov     rdx, rbx; int
0x14003383b  mov     [rsp+78h+BufferAddress], rax; BufferAddress
0x140033840  mov     rcx, rsi; int
0x140033843  mov     [rsp+78h+var_58], bpl; char
0x140033848  call    ClasspDeviceIssueReportSupportedOperationCodesCommand
0x14003384d  mov     edi, eax
0x14003384f  test    eax, eax
0x140033851  js      short loc_1400338BD
0x140033853  mov     dl, bpl
0x140033856  mov     rcx, rsi
0x140033859  call    ClasspGetDurationLimitCommandInfo
0x14003385e  mov     cl, byte ptr [rsp+78h+var_38]
0x140033862  mov     r8, rax
0x140033865  and     cl, r13b
0x140033868  movzx   edx, cl
0x14003386b  movzx   ecx, word ptr [rax]
0x14003386e  mov     eax, 0FFF7h
0x140033873  and     cx, ax
0x140033876  shl     dx, 3
0x14003387a  or      dx, cx
0x14003387d  mov     [r8], dx
0x140033881  mov     al, byte ptr [rsp+78h+var_38+1]
0x140033885  mov     r15b, byte ptr [rsp+78h+var_38]
0x14003388a  shr     al, 3
0x14003388d  and     r15b, r13b
0x140033890  and     al, 3
0x140033892  movzx   ecx, al
0x140033895  mov     eax, 0FFCFh
0x14003389a  and     dx, ax
0x14003389d  shl     cx, 4
0x1400338a1  or      cx, dx
0x1400338a4  mov     [r8], cx
0x1400338a8  mov     r14b, byte ptr [rsp+78h+var_38+1]
0x1400338ad  shr     r14b, 3
0x1400338b1  and     r14b, 3
0x1400338b5  or      cx, r13w
0x1400338b9  mov     [r8], cx
0x1400338bd  cmp     cs:ClassPnPETWEnabled, 0
0x1400338c4  jz      short loc_1400338DF
0x1400338c6  mov     rdx, [rsi+8]
0x1400338ca  mov     r9b, bpl
0x1400338cd  mov     [rsp+78h+var_50], r14b
0x1400338d2  mov     r8d, edi
0x1400338d5  mov     [rsp+78h+var_58], r15b
0x1400338da  call    ClasspQueryCDLSupportAndModePageEvent
0x1400338df  test    rbx, rbx
0x1400338e2  jz      short loc_1400338F5
0x1400338e4  xor     edx, edx; Tag
0x1400338e6  mov     rcx, rbx; P
0x1400338e9  call    cs:__imp_ExFreePoolWithTag
0x1400338f0  nop     dword ptr [rax+rax+00h]
0x1400338f5  mov     eax, edi
0x1400338f7  mov     rcx, [rsp+78h+var_30]
0x1400338fc  xor     rcx, rsp; StackCookie
0x1400338ff  call    __security_check_cookie
0x140033904  lea     r11, [rsp+78h+var_28]
0x140033909  mov     rbx, [r11+40h]
0x14003390d  mov     rbp, [r11+48h]
0x140033911  mov     rsp, r11
0x140033914  pop     r15
0x140033916  pop     r14
0x140033918  pop     r13
0x14003391a  pop     rdi
0x14003391b  pop     rsi
0x14003391c  retn
```
