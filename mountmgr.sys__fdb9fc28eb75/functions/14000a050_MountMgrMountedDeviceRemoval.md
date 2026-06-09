# MountMgrMountedDeviceRemoval

- ea: `0x14000a050`
- end: `0x14000a503`
- name: `MountMgrMountedDeviceRemoval`
- size: `1203`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `4`
- tags: `reparse_path, registry_config, broker_com_uri`

## callers

- `0x14000f518`
- `0x140019980`
- `0x140019f70`

## callees

- `0x14000a050`
- `0x14000a510`
- `0x14000b588`
- `0x140018cd0`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x14000a0ad`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14000a0e1`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14000a0ad`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14000a0e1`
- `ntoskrnl!RtlDeleteRegistryValue` at `0x14000a17b`
- `ntoskrnl!RtlDeleteRegistryValue` at `0x14000a17b`
- `ntoskrnl!IoUnregisterPlugPlayNotification` at `0x14000a4b7`
- `ntoskrnl!IoUnregisterPlugPlayNotification` at `0x14000a4b7`
- `ntoskrnl!KeReleaseMutex` at `0x14000a105`
- `ntoskrnl!KeReleaseMutex` at `0x14000a105`
- `ntoskrnl!ExAllocatePool2` at `0x14000a224`
- `ntoskrnl!ExAllocatePool2` at `0x14000a224`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a18d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a19e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a1e9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a1fa`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a2e3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a2f4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a33f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a350`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a399`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a3aa`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a437`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a448`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a472`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a48d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a49f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a4c8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a18d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a19e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a1e9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a1fa`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a2e3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a2f4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a33f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a350`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a399`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a3aa`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a437`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a448`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a472`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a48d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a49f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a4c8`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000a083`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000a083`

## string_xrefs

- `0x14000a172`: `\Registry\Machine\System\MountedDevices`

## pseudocode

```c
__int64 __fastcall MountMgrMountedDeviceRemoval(struct _KMUTANT *a1, const UNICODE_STRING *a2, char a3)
{
  struct _KMUTANT *v3; // rbp
  struct _LIST_ENTRY *Blink; // rdi
  struct _LIST_ENTRY *p_Blink; // rsi
  struct _LIST_ENTRY **v9; // rdi
  UNICODE_STRING *v10; // rbx
  LONG v11; // eax
  struct _LIST_ENTRY **v12; // rcx
  void **p_Flink; // r15
  char *v15; // r14
  void **v16; // rax
  void **v17; // r15
  void *v18; // r14
  void **v19; // rax
  struct _LIST_ENTRY *Pool2; // r8
  struct _LIST_ENTRY *v21; // rdx
  struct _LIST_ENTRY *v22; // r15
  struct _LIST_ENTRY *v23; // r12
  struct _LIST_ENTRY *Flink; // r14
  struct _LIST_ENTRY *v25; // rax
  struct _LIST_ENTRY *v26; // rax
  void **v27; // r15
  char *v28; // r14
  void **v29; // rax
  void **v30; // r15
  void *v31; // r14
  void **v32; // rax
  struct _LIST_ENTRY *v33; // rax
  struct _LIST_ENTRY *v34; // rcx
  struct _LIST_ENTRY *i; // r12
  struct _LIST_ENTRY *j; // r14
  struct _LIST_ENTRY *v37; // rax
  struct _LIST_ENTRY *v38; // r15
  struct _LIST_ENTRY *v39; // rcx
  void **Buffer; // rax

  v3 = a1 + 1;
  KeWaitForSingleObject(&a1[1], Executive, 0, 0, 0);
  Blink = a1->Header.WaitListHead.Blink;
  p_Blink = (struct _LIST_ENTRY *)&a1->Header.WaitListHead.Blink;
  ++*(_QWORD *)&a1[6].Header.Lock;
  if ( Blink == (struct _LIST_ENTRY *)&a1->Header.WaitListHead.Blink )
  {
LABEL_4:
    if ( a3 )
      goto LABEL_8;
    v9 = &a1->MutantListEntry.Blink;
    v10 = (UNICODE_STRING *)a1->MutantListEntry.Blink;
    if ( v10 == (UNICODE_STRING *)v9 )
      goto LABEL_8;
    while ( 1 )
    {
      v11 = RtlCompareUnicodeString(v10 + 4, a2, 1u);
      v12 = *(struct _LIST_ENTRY ***)&v10->Length;
      if ( !v11 )
        break;
      v10 = *(UNICODE_STRING **)&v10->Length;
      if ( v12 == v9 )
        goto LABEL_8;
    }
    if ( v12[1] == (struct _LIST_ENTRY *)v10 )
    {
      Buffer = (void **)v10->Buffer;
      if ( *Buffer == v10 )
      {
        *Buffer = v12;
        v12[1] = (struct _LIST_ENTRY *)Buffer;
        MountMgrFreeDeadDeviceInfo(v10);
        goto LABEL_8;
      }
    }
    goto LABEL_63;
  }
  while ( RtlCompareUnicodeString((PCUNICODE_STRING)&Blink[4], a2, 1u) )
  {
    Blink = Blink->Flink;
    if ( Blink == p_Blink )
      goto LABEL_4;
  }
  if ( BYTE1(Blink[8].Flink) == a3 )
  {
    if ( HIBYTE(Blink[8].Flink) )
    {
      p_Flink = (void **)&Blink[1].Flink;
      while ( 1 )
      {
        v15 = (char *)*p_Flink;
        if ( *p_Flink == p_Flink )
          break;
        if ( *((void ***)v15 + 1) != p_Flink )
          goto LABEL_63;
        v16 = *(void ***)v15;
        if ( *(char **)(*(_QWORD *)v15 + 8LL) != v15 )
          goto LABEL_63;
        *p_Flink = v16;
        v16[1] = p_Flink;
        GlobalDeleteSymbolicLink(v15 + 24);
        RtlDeleteRegistryValue(0, L"\\Registry\\Machine\\System\\MountedDevices", *((PCWSTR *)v15 + 4));
        ExFreePoolWithTag(*((PVOID *)v15 + 4), 0);
        ExFreePoolWithTag(v15, 0);
      }
      DeleteNoDriveLetterEntry(Blink[6].Flink);
    }
    else
    {
      Pool2 = 0;
      if ( BYTE2(Blink[8].Flink) )
      {
        Pool2 = (struct _LIST_ENTRY *)ExAllocatePool2(258, 40, 1098149453);
        if ( !Pool2 )
          BYTE2(Blink[8].Flink) = 0;
      }
      if ( BYTE2(Blink[8].Flink) )
      {
        v21 = a1[3].Header.WaitListHead.Blink;
        if ( v21->Flink != &a1[3].Header.WaitListHead )
          goto LABEL_63;
        Pool2->Flink = &a1[3].Header.WaitListHead;
        v22 = Pool2 + 1;
        Pool2->Blink = v21;
        v23 = Blink + 1;
        v21->Flink = Pool2;
        a1[3].Header.WaitListHead.Blink = Pool2;
        Pool2[1].Blink = Pool2 + 1;
        Pool2[1].Flink = Pool2 + 1;
        Pool2[2].Flink = Blink[6].Flink;
        while ( 1 )
        {
          Flink = v23->Flink;
          if ( v23->Flink == v23 )
            break;
          if ( Flink->Blink != v23 )
            goto LABEL_63;
          v25 = Flink->Flink;
          if ( Flink->Flink->Blink != Flink )
            goto LABEL_63;
          v23->Flink = v25;
          v25->Blink = v23;
          if ( LOBYTE(Flink[1].Flink) )
          {
            v26 = v22->Blink;
            if ( v26->Flink != v22 )
              goto LABEL_63;
            Flink->Flink = v22;
            Flink->Blink = v26;
            v26->Flink = Flink;
            v22->Blink = Flink;
          }
          else
          {
            GlobalDeleteSymbolicLink(&Flink[1].Blink);
            ExFreePoolWithTag(Flink[2].Flink, 0);
            ExFreePoolWithTag(Flink, 0);
          }
        }
      }
      else
      {
        v27 = (void **)&Blink[1].Flink;
        while ( 1 )
        {
          v28 = (char *)*v27;
          if ( *v27 == v27 )
            break;
          if ( *((void ***)v28 + 1) != v27 )
            goto LABEL_63;
          v29 = *(void ***)v28;
          if ( *(char **)(*(_QWORD *)v28 + 8LL) != v28 )
            goto LABEL_63;
          *v27 = v29;
          v29[1] = v27;
          GlobalDeleteSymbolicLink(v28 + 24);
          ExFreePoolWithTag(*((PVOID *)v28 + 4), 0);
          ExFreePoolWithTag(v28, 0);
        }
      }
    }
    v17 = (void **)&Blink[2].Flink;
    while ( 1 )
    {
      v18 = *v17;
      if ( *v17 == v17 )
        break;
      if ( *((void ***)v18 + 1) != v17 )
        goto LABEL_63;
      v19 = *(void ***)v18;
      if ( *(void **)(*(_QWORD *)v18 + 8LL) != v18 )
        goto LABEL_63;
      *v17 = v19;
      v19[1] = v17;
      ExFreePoolWithTag(*((PVOID *)v18 + 2), 0);
      ExFreePoolWithTag(v18, 0);
    }
    v30 = (void **)&Blink[3].Flink;
    while ( 1 )
    {
      v31 = *v30;
      if ( *v30 == v30 )
        break;
      if ( *((void ***)v31 + 1) != v30 )
        goto LABEL_63;
      v32 = *(void ***)v31;
      if ( *(void **)(*(_QWORD *)v31 + 8LL) != v31 )
        goto LABEL_63;
      *v30 = v32;
      v32[1] = v30;
      *(_BYTE *)(*((_QWORD *)v31 + 2) + 132LL) = 1;
      ExFreePoolWithTag(*((PVOID *)v31 + 4), 0);
      ExFreePoolWithTag(v31, 0);
    }
    v33 = Blink->Flink;
    if ( Blink->Flink->Blink == Blink )
    {
      v34 = Blink->Blink;
      if ( v34->Flink == Blink )
      {
        v34->Flink = v33;
        v33->Blink = v34;
        for ( i = p_Blink->Flink; i != p_Blink; i = i->Flink )
        {
          for ( j = i[3].Flink; j != &i[3]; j = j->Flink )
          {
            if ( j[1].Flink == Blink )
            {
              i[11].Flink = (struct _LIST_ENTRY *)++*(_QWORD *)&a1[6].Header.Lock;
              v37 = j->Flink;
              if ( j->Flink->Blink != j )
                goto LABEL_63;
              v38 = j->Blink;
              if ( v38->Flink != j )
                goto LABEL_63;
              v38->Flink = v37;
              v37->Blink = v38;
              ExFreePoolWithTag(j[2].Flink, 0);
              ExFreePoolWithTag(j, 0);
              j = v38;
            }
          }
        }
        ExFreePoolWithTag(Blink[4].Blink, 0);
        if ( !BYTE2(Blink[8].Flink) )
          ExFreePoolWithTag(Blink[6].Flink, 0);
        ExFreePoolWithTag(Blink[5].Blink, 0);
        v39 = Blink[9].Flink;
        if ( v39 )
          IoUnregisterPlugPlayNotification(v39);
        ExFreePoolWithTag(Blink, 0);
        goto LABEL_8;
      }
    }
LABEL_63:
    __fastfail(3u);
  }
LABEL_8:
  KeReleaseMutex(v3, 0);
  return 0;
}

```

## disassembly

```asm
0x14000a050  push    rbx
0x14000a052  push    rbp
0x14000a053  push    rsi
0x14000a054  push    rdi
0x14000a055  push    r12
0x14000a057  push    r13
0x14000a059  push    r14
0x14000a05b  push    r15
0x14000a05d  sub     rsp, 38h
0x14000a061  lea     rbp, [rcx+38h]
0x14000a065  mov     [rsp+78h+Timeout], 0; Timeout
0x14000a06e  movzx   r14d, r8b
0x14000a072  mov     r15, rdx
0x14000a075  mov     rbx, rcx
0x14000a078  xor     r9d, r9d; Alertable
0x14000a07b  mov     rcx, rbp; Object
0x14000a07e  xor     r8d, r8d; WaitMode
0x14000a081  xor     edx, edx; WaitReason
0x14000a083  call    cs:__imp_KeWaitForSingleObject
0x14000a08a  nop     dword ptr [rax+rax+00h]
0x14000a08f  mov     rdi, [rbx+10h]
0x14000a093  lea     rsi, [rbx+10h]
0x14000a097  inc     qword ptr [rbx+150h]
0x14000a09e  cmp     rdi, rsi
0x14000a0a1  jz      short loc_14000A0C5
0x14000a0a3  lea     rcx, [rdi+40h]; String1
0x14000a0a7  mov     r8b, 1; CaseInSensitive
0x14000a0aa  mov     rdx, r15; String2
0x14000a0ad  call    cs:__imp_RtlCompareUnicodeString
0x14000a0b4  nop     dword ptr [rax+rax+00h]
0x14000a0b9  test    eax, eax
0x14000a0bb  jz      short loc_14000A125
0x14000a0bd  mov     rdi, [rdi]
0x14000a0c0  cmp     rdi, rsi
0x14000a0c3  jnz     short loc_14000A0A3
0x14000a0c5  test    r14b, r14b
0x14000a0c8  jnz     short loc_14000A100
0x14000a0ca  lea     rdi, [rbx+20h]
0x14000a0ce  mov     rbx, [rbx+20h]
0x14000a0d2  cmp     rbx, rdi
0x14000a0d5  jz      short loc_14000A100
0x14000a0d7  lea     rcx, [rbx+40h]; String1
0x14000a0db  mov     r8b, 1; CaseInSensitive
0x14000a0de  mov     rdx, r15; String2
0x14000a0e1  call    cs:__imp_RtlCompareUnicodeString
0x14000a0e8  nop     dword ptr [rax+rax+00h]
0x14000a0ed  mov     rcx, [rbx]
0x14000a0f0  test    eax, eax
0x14000a0f2  jz      loc_14000A4D9
0x14000a0f8  mov     rbx, rcx
0x14000a0fb  cmp     rcx, rdi
0x14000a0fe  jnz     short loc_14000A0D7
0x14000a100  xor     edx, edx; Wait
0x14000a102  mov     rcx, rbp; Mutex
0x14000a105  call    cs:__imp_KeReleaseMutex
0x14000a10c  nop     dword ptr [rax+rax+00h]
0x14000a111  xor     eax, eax
0x14000a113  add     rsp, 38h
0x14000a117  pop     r15
0x14000a119  pop     r14
0x14000a11b  pop     r13
0x14000a11d  pop     r12
0x14000a11f  pop     rdi
0x14000a120  pop     rsi
0x14000a121  pop     rbp
0x14000a122  pop     rbx
0x14000a123  retn
0x14000a125  cmp     [rdi+81h], r14b
0x14000a12c  jnz     short loc_14000A100
0x14000a12e  cmp     byte ptr [rdi+87h], 0
0x14000a135  jz      loc_14000A208
0x14000a13b  lea     r15, [rdi+10h]
0x14000a13f  mov     r14, [r15]
0x14000a142  cmp     r14, r15
0x14000a145  jz      short loc_14000A1AC
0x14000a147  cmp     [r14+8], r15
0x14000a14b  jnz     loc_14000A4FC
0x14000a151  mov     rax, [r14]
0x14000a154  cmp     [rax+8], r14
0x14000a158  jnz     loc_14000A4FC
0x14000a15e  mov     [r15], rax
0x14000a161  lea     rcx, [r14+18h]
0x14000a165  mov     [rax+8], r15
0x14000a169  call    GlobalDeleteSymbolicLink
0x14000a16e  mov     r8, [r14+20h]; ValueName
0x14000a172  lea     rdx, Path; "\\Registry\\Machine\\System\\MountedDev"...
0x14000a179  xor     ecx, ecx; RelativeTo
0x14000a17b  call    cs:__imp_RtlDeleteRegistryValue
0x14000a182  nop     dword ptr [rax+rax+00h]
0x14000a187  mov     rcx, [r14+20h]; P
0x14000a18b  xor     edx, edx; Tag
0x14000a18d  call    cs:__imp_ExFreePoolWithTag
0x14000a194  nop     dword ptr [rax+rax+00h]
0x14000a199  xor     edx, edx; Tag
0x14000a19b  mov     rcx, r14; P
0x14000a19e  call    cs:__imp_ExFreePoolWithTag
0x14000a1a5  nop     dword ptr [rax+rax+00h]
0x14000a1aa  jmp     short loc_14000A13F
0x14000a1ac  mov     rcx, [rdi+60h]
0x14000a1b0  call    DeleteNoDriveLetterEntry
0x14000a1b5  lea     r15, [rdi+20h]
0x14000a1b9  mov     r14, [r15]
0x14000a1bc  cmp     r14, r15
0x14000a1bf  jz      loc_14000A35E
0x14000a1c5  cmp     [r14+8], r15
0x14000a1c9  jnz     loc_14000A4FC
0x14000a1cf  mov     rax, [r14]
0x14000a1d2  cmp     [rax+8], r14
0x14000a1d6  jnz     loc_14000A4FC
0x14000a1dc  mov     [r15], rax
0x14000a1df  xor     edx, edx; Tag
0x14000a1e1  mov     [rax+8], r15
0x14000a1e5  mov     rcx, [r14+10h]; P
0x14000a1e9  call    cs:__imp_ExFreePoolWithTag
0x14000a1f0  nop     dword ptr [rax+rax+00h]
0x14000a1f5  xor     edx, edx; Tag
0x14000a1f7  mov     rcx, r14; P
0x14000a1fa  call    cs:__imp_ExFreePoolWithTag
0x14000a201  nop     dword ptr [rax+rax+00h]
0x14000a206  jmp     short loc_14000A1B9
0x14000a208  xor     r8d, r8d
0x14000a20b  cmp     [rdi+82h], r8b
0x14000a212  jz      short loc_14000A23E
0x14000a214  mov     edx, 28h ; '('
0x14000a219  mov     ecx, 102h
0x14000a21e  mov     r8d, 41746E4Dh
0x14000a224  call    cs:__imp_ExAllocatePool2
0x14000a22b  nop     dword ptr [rax+rax+00h]
0x14000a230  mov     r8, rax
0x14000a233  test    rax, rax
0x14000a236  jnz     short loc_14000A23E
0x14000a238  mov     [rdi+82h], al
0x14000a23e  cmp     byte ptr [rdi+82h], 0
0x14000a245  jz      loc_14000A302
0x14000a24b  lea     rcx, [rbx+0B0h]
0x14000a252  mov     rdx, [rcx+8]
0x14000a256  cmp     [rdx], rcx
0x14000a259  jnz     loc_14000A4FC
0x14000a25f  mov     [r8], rcx
0x14000a262  lea     r15, [r8+10h]
0x14000a266  mov     [r8+8], rdx
0x14000a26a  lea     r12, [rdi+10h]
0x14000a26e  mov     [rdx], r8
0x14000a271  mov     [rcx+8], r8
0x14000a275  mov     [r15+8], r15
0x14000a279  mov     [r15], r15
0x14000a27c  mov     rax, [rdi+60h]
0x14000a280  mov     [r8+20h], rax
0x14000a284  mov     r14, [r12]
0x14000a288  cmp     r14, r12
0x14000a28b  jz      loc_14000A1B5
0x14000a291  cmp     [r14+8], r12
0x14000a295  jnz     loc_14000A4FC
0x14000a29b  mov     rax, [r14]
0x14000a29e  cmp     [rax+8], r14
0x14000a2a2  jnz     loc_14000A4FC
0x14000a2a8  mov     [r12], rax
0x14000a2ac  mov     [rax+8], r12
0x14000a2b0  cmp     byte ptr [r14+10h], 0
0x14000a2b5  jz      short loc_14000A2D4
0x14000a2b7  mov     rax, [r15+8]
0x14000a2bb  cmp     [rax], r15
0x14000a2be  jnz     loc_14000A4FC
0x14000a2c4  mov     [r14], r15
0x14000a2c7  mov     [r14+8], rax
0x14000a2cb  mov     [rax], r14
0x14000a2ce  mov     [r15+8], r14
0x14000a2d2  jmp     short loc_14000A284
0x14000a2d4  lea     rcx, [r14+18h]
0x14000a2d8  call    GlobalDeleteSymbolicLink
0x14000a2dd  mov     rcx, [r14+20h]; P
0x14000a2e1  xor     edx, edx; Tag
0x14000a2e3  call    cs:__imp_ExFreePoolWithTag
0x14000a2ea  nop     dword ptr [rax+rax+00h]
0x14000a2ef  xor     edx, edx; Tag
0x14000a2f1  mov     rcx, r14; P
0x14000a2f4  call    cs:__imp_ExFreePoolWithTag
0x14000a2fb  nop     dword ptr [rax+rax+00h]
0x14000a300  jmp     short loc_14000A284
0x14000a302  lea     r15, [rdi+10h]
0x14000a306  mov     r14, [r15]
0x14000a309  cmp     r14, r15
0x14000a30c  jz      loc_14000A1B5
0x14000a312  cmp     [r14+8], r15
0x14000a316  jnz     loc_14000A4FC
0x14000a31c  mov     rax, [r14]
0x14000a31f  cmp     [rax+8], r14
0x14000a323  jnz     loc_14000A4FC
0x14000a329  mov     [r15], rax
0x14000a32c  lea     rcx, [r14+18h]
0x14000a330  mov     [rax+8], r15
0x14000a334  call    GlobalDeleteSymbolicLink
0x14000a339  mov     rcx, [r14+20h]; P
0x14000a33d  xor     edx, edx; Tag
0x14000a33f  call    cs:__imp_ExFreePoolWithTag
0x14000a346  nop     dword ptr [rax+rax+00h]
0x14000a34b  xor     edx, edx; Tag
0x14000a34d  mov     rcx, r14; P
0x14000a350  call    cs:__imp_ExFreePoolWithTag
0x14000a357  nop     dword ptr [rax+rax+00h]
0x14000a35c  jmp     short loc_14000A306
0x14000a35e  lea     r15, [rdi+30h]
0x14000a362  mov     r14, [r15]
0x14000a365  cmp     r14, r15
0x14000a368  jz      short loc_14000A3B8
0x14000a36a  cmp     [r14+8], r15
0x14000a36e  jnz     loc_14000A4FC
0x14000a374  mov     rax, [r14]
0x14000a377  cmp     [rax+8], r14
0x14000a37b  jnz     loc_14000A4FC
0x14000a381  mov     [r15], rax
0x14000a384  xor     edx, edx; Tag
0x14000a386  mov     [rax+8], r15
0x14000a38a  mov     rax, [r14+10h]
0x14000a38e  mov     byte ptr [rax+84h], 1
0x14000a395  mov     rcx, [r14+20h]; P
0x14000a399  call    cs:__imp_ExFreePoolWithTag
0x14000a3a0  nop     dword ptr [rax+rax+00h]
0x14000a3a5  xor     edx, edx; Tag
0x14000a3a7  mov     rcx, r14; P
0x14000a3aa  call    cs:__imp_ExFreePoolWithTag
0x14000a3b1  nop     dword ptr [rax+rax+00h]
0x14000a3b6  jmp     short loc_14000A362
0x14000a3b8  mov     rax, [rdi]
0x14000a3bb  cmp     [rax+8], rdi
0x14000a3bf  jnz     loc_14000A4FC
0x14000a3c5  mov     rcx, [rdi+8]
0x14000a3c9  cmp     [rcx], rdi
0x14000a3cc  jnz     loc_14000A4FC
0x14000a3d2  mov     [rcx], rax
0x14000a3d5  mov     [rax+8], rcx
0x14000a3d9  mov     r12, [rsi]
0x14000a3dc  cmp     r12, rsi
0x14000a3df  jz      loc_14000A46C
0x14000a3e5  mov     r14, [r12+30h]
0x14000a3ea  lea     r13, [r12+30h]
0x14000a3ef  cmp     r14, r13
0x14000a3f2  jz      short loc_14000A45F
0x14000a3f4  cmp     [r14+10h], rdi
0x14000a3f8  jnz     short loc_14000A457
0x14000a3fa  inc     qword ptr [rbx+150h]
0x14000a401  mov     rax, [rbx+150h]
0x14000a408  mov     [r12+0B0h], rax
0x14000a410  mov     rax, [r14]
0x14000a413  cmp     [rax+8], r14
0x14000a417  jnz     loc_14000A4FC
0x14000a41d  mov     r15, [r14+8]
0x14000a421  cmp     [r15], r14
0x14000a424  jnz     loc_14000A4FC
0x14000a42a  mov     [r15], rax
0x14000a42d  xor     edx, edx; Tag
0x14000a42f  mov     [rax+8], r15
0x14000a433  mov     rcx, [r14+20h]; P
0x14000a437  call    cs:__imp_ExFreePoolWithTag
0x14000a43e  nop     dword ptr [rax+rax+00h]
0x14000a443  xor     edx, edx; Tag
0x14000a445  mov     rcx, r14; P
0x14000a448  call    cs:__imp_ExFreePoolWithTag
0x14000a44f  nop     dword ptr [rax+rax+00h]
0x14000a454  mov     r14, r15
0x14000a457  mov     r14, [r14]
0x14000a45a  cmp     r14, r13
0x14000a45d  jnz     short loc_14000A3F4
0x14000a45f  mov     r12, [r12]
0x14000a463  cmp     r12, rsi
0x14000a466  jnz     loc_14000A3E5
0x14000a46c  mov     rcx, [rdi+48h]; P
0x14000a470  xor     edx, edx; Tag
0x14000a472  call    cs:__imp_ExFreePoolWithTag
0x14000a479  nop     dword ptr [rax+rax+00h]
0x14000a47e  cmp     byte ptr [rdi+82h], 0
0x14000a485  jnz     short loc_14000A499
0x14000a487  mov     rcx, [rdi+60h]; P
0x14000a48b  xor     edx, edx; Tag
0x14000a48d  call    cs:__imp_ExFreePoolWithTag
0x14000a494  nop     dword ptr [rax+rax+00h]
0x14000a499  mov     rcx, [rdi+58h]; P
0x14000a49d  xor     edx, edx; Tag
0x14000a49f  call    cs:__imp_ExFreePoolWithTag
0x14000a4a6  nop     dword ptr [rax+rax+00h]
0x14000a4ab  mov     rcx, [rdi+90h]; NotificationEntry
0x14000a4b2  test    rcx, rcx
0x14000a4b5  jz      short loc_14000A4C3
0x14000a4b7  call    cs:__imp_IoUnregisterPlugPlayNotification
0x14000a4be  nop     dword ptr [rax+rax+00h]
0x14000a4c3  xor     edx, edx; Tag
0x14000a4c5  mov     rcx, rdi; P
0x14000a4c8  call    cs:__imp_ExFreePoolWithTag
0x14000a4cf  nop     dword ptr [rax+rax+00h]
0x14000a4d4  jmp     loc_14000A100
0x14000a4d9  cmp     [rcx+8], rbx
0x14000a4dd  jnz     short loc_14000A4FC
0x14000a4df  mov     rax, [rbx+8]
0x14000a4e3  cmp     [rax], rbx
0x14000a4e6  jnz     short loc_14000A4FC
0x14000a4e8  mov     [rax], rcx
0x14000a4eb  mov     [rcx+8], rax
0x14000a4ef  mov     rcx, rbx; P
0x14000a4f2  call    MountMgrFreeDeadDeviceInfo
0x14000a4f7  jmp     loc_14000A100
  ... truncated ...
```
