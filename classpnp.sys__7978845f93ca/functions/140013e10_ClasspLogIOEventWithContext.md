# ClasspLogIOEventWithContext

- ea: `0x140013e10`
- end: `0x140014109`
- name: `ClasspLogIOEventWithContext`
- size: `761`
- prototype: `IO_WORKITEM_ROUTINE`
- caller_count: `0`
- callee_count: `6`
- tags: `reparse_path, loader_planting`

## callees

- `0x1400134a0`
- `0x140013e10`
- `0x140014110`
- `0x14001fc38`
- `0x14003e640`
- `0x14003e940`

## import_xrefs

- `ntoskrnl!IoWriteErrorLogEntry` at `0x140013f80`
- `ntoskrnl!IoWriteErrorLogEntry` at `0x140013f80`
- `ntoskrnl!IoFreeWorkItem` at `0x140013fc3`
- `ntoskrnl!IoFreeWorkItem` at `0x140013fc3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013fd4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400140f8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013fd4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400140f8`
- `ntoskrnl!IoAllocateErrorLogEntry` at `0x140013e87`
- `ntoskrnl!IoAllocateErrorLogEntry` at `0x140013e87`
- `ntoskrnl!IoGetDeviceProperty` at `0x14001402b`
- `ntoskrnl!IoGetDeviceProperty` at `0x1400403f8`
- `ntoskrnl!IoGetDeviceProperty` at `0x14001402b`
- `ntoskrnl!IoGetDeviceProperty` at `0x1400403f8`

## pseudocode

```c
void __fastcall ClasspLogIOEventWithContext(PDEVICE_OBJECT DeviceObject, _DWORD *Context)
{
  int v2; // eax
  PDEVICE_OBJECT *DeviceExtension; // r13
  ULONG v6; // eax
  void *v7; // r12
  unsigned int v8; // esi
  unsigned int v9; // edi
  unsigned int v10; // edx
  _WORD *ErrorLogEntry; // rax
  _WORD *v12; // rbx
  void *v13; // rcx
  unsigned int v14; // eax
  const void *v15; // rdx
  signed int v16; // edi
  int v17; // eax
  char *v18; // rbp
  __int64 v19; // rsi
  __int64 v20; // rcx
  int v21; // edi
  void *v22; // rcx
  char *v23; // rbp
  __int64 v24; // rsi
  __int64 v25; // rcx
  int v26; // edi
  wchar_t *v27; // rbp
  __int64 v28; // rcx
  int v29; // edi
  wchar_t *v30; // rbp
  ULONG BufferLength; // [rsp+70h] [rbp+8h] BYREF
  ULONG ResultLength; // [rsp+78h] [rbp+10h] BYREF

  v2 = Context[6];
  DeviceExtension = (PDEVICE_OBJECT *)DeviceObject->DeviceExtension;
  BufferLength = 0;
  if ( v2 != -2147221351 )
  {
    if ( v2 == -2147221349 )
    {
      v6 = 104;
      goto LABEL_5;
    }
    if ( v2 != -1073479526 )
    {
      v6 = 0;
      goto LABEL_5;
    }
  }
  if ( IoGetDeviceProperty(DeviceExtension[64], DevicePropertyPhysicalDeviceObjectName, 0, 0, &BufferLength) == -1073741789
    && BufferLength )
  {
    v6 = BufferLength + 60;
  }
  else
  {
    v6 = 60;
    BufferLength = 0;
  }
LABEL_5:
  v7 = *(void **)Context;
  v8 = (Context[4] + 3) & 0xFFFFFFFC;
  v9 = 240;
  v10 = v6 + v8 + 44;
  if ( v10 > 0xF0 )
  {
    if ( v8 )
    {
      if ( (unsigned __int64)v10 - 240 >= v8 )
        v8 = 0;
      else
        v8 = (240 - (v6 + 44)) & 0xFFFFFFFC;
    }
  }
  else
  {
    v9 = v6 + v8 + 44;
  }
  ErrorLogEntry = IoAllocateErrorLogEntry(DeviceObject, v9);
  v12 = ErrorLogEntry;
  if ( ErrorLogEntry )
  {
    memset(ErrorLogEntry, 0, v9);
    *v12 = 271;
    v12[1] = v8 + 4;
    v12[3] = v8 + 44;
    *((_DWORD *)v12 + 3) = Context[6];
    *((_DWORD *)v12 + 10) = (*((unsigned __int8 *)Context + 21)
                           | ((*((unsigned __int8 *)Context + 20) | (*((unsigned __int8 *)Context + 22) << 8)) << 8)) << 8;
    v13 = v12 + 22;
    v14 = Context[4];
    v15 = (const void *)*((_QWORD *)Context + 1);
    if ( v8 <= v14 )
    {
      memmove(v13, v15, v8);
    }
    else
    {
      memmove(v13, v15, v14);
      memset((char *)v12 + (unsigned int)Context[4] + 44, 45, v8 - Context[4]);
    }
    v16 = v9 - (unsigned __int16)v12[3];
    v17 = Context[6];
    v18 = (char *)v12 + (unsigned __int16)v12[1] + 40;
    if ( v17 != -2147221351 )
    {
      if ( v17 == -2147221349 )
      {
        if ( RtlStringCbPrintfW(
               (_WORD *)((char *)v12 + (unsigned __int16)v12[1] + 40),
               v16,
               L"0x%I64x",
               *((_QWORD *)Context + 4)) >= 0 )
        {
          ++v12[2];
          v24 = -1;
          v25 = -1;
          do
            ++v25;
          while ( *(_WORD *)&v18[2 * v25] );
          v26 = v16 - (2 * v25 + 2);
          v27 = (wchar_t *)&v18[2 * v25 + 2];
          if ( RtlStringCbPrintfW(v27, v26, (NTSTRSAFE_PCWSTR)"%\x00d", (unsigned int)Context[10]) >= 0 )
          {
            ++v12[2];
            v28 = -1;
            do
              ++v28;
            while ( v27[v28] );
            v29 = v26 - (2 * v28 + 2);
            v30 = &v27[v28];
            if ( RtlStringCbPrintfW(v30 + 1, v29, (NTSTRSAFE_PCWSTR)"%\x00d", (unsigned int)Context[12]) >= 0 )
            {
              ++v12[2];
              do
                ++v24;
              while ( v30[v24 + 1] );
              if ( RtlStringCbPrintfW(
                     &v30[v24 + 2],
                     v29 - (2 * (int)v24 + 2),
                     (NTSTRSAFE_PCWSTR)"%\x00d",
                     (unsigned int)Context[14]) >= 0 )
                goto LABEL_55;
            }
          }
        }
        goto LABEL_15;
      }
      if ( v17 != -1073479526 )
        goto LABEL_15;
    }
    if ( RtlStringCbPrintfW(
           (_WORD *)((char *)v12 + (unsigned __int16)v12[1] + 40),
           v16,
           L"0x%I64x",
           *((_QWORD *)Context + 4)) >= 0 )
    {
      ++v12[2];
      v19 = -1;
      v20 = -1;
      do
        ++v20;
      while ( *(_WORD *)&v18[2 * v20] );
      v21 = v16 - (2 * v20 + 2);
      if ( v21 > 0 )
      {
        v23 = &v18[2 * v20];
        if ( RtlStringCbPrintfW((NTSTRSAFE_PWSTR)v23 + 1, v21, (NTSTRSAFE_PCWSTR)"%\x00d", (unsigned int)Context[10]) >= 0 )
        {
          ++v12[2];
          do
            ++v19;
          while ( *(_WORD *)&v23[2 * v19 + 2] );
          if ( v21 - (2 * (int)v19 + 2) >= (int)BufferLength )
          {
            if ( BufferLength )
            {
              ResultLength = 0;
              if ( IoGetDeviceProperty(
                     DeviceExtension[64],
                     DevicePropertyPhysicalDeviceObjectName,
                     BufferLength,
                     &v23[2 * v19 + 4],
                     &ResultLength) >= 0 )
              {
                if ( ResultLength )
LABEL_55:
                  ++v12[2];
              }
            }
          }
        }
      }
    }
LABEL_15:
    IoWriteErrorLogEntry(v12);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 86, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids, DeviceObject);
    }
  }
  ClassReleaseRemoveLock(DeviceObject, v7);
  v22 = (void *)*((_QWORD *)Context + 1);
  if ( v22 )
    ExFreePoolWithTag(v22, 0);
  if ( v7 )
    IoFreeWorkItem((PIO_WORKITEM)v7);
  ExFreePoolWithTag(Context, 0);
}

```

## disassembly

```asm
0x140013e10  mov     [rsp+arg_10], rbx
0x140013e15  push    rbp
0x140013e16  push    rsi
0x140013e17  push    rdi
0x140013e18  push    r12
0x140013e1a  push    r13
0x140013e1c  push    r14
0x140013e1e  push    r15
0x140013e20  sub     rsp, 30h
0x140013e24  mov     eax, [rdx+18h]
0x140013e27  xor     ebx, ebx
0x140013e29  mov     r13, [rcx+40h]
0x140013e2d  mov     r14, rdx
0x140013e30  mov     [rsp+68h+BufferLength], ebx
0x140013e34  mov     r15, rcx
0x140013e37  cmp     eax, 80040099h
0x140013e3c  jz      loc_140014010
0x140013e42  cmp     eax, 8004009Bh
0x140013e47  jz      loc_140014006
0x140013e4d  cmp     eax, 0C004009Ah
0x140013e52  jz      loc_140014010
0x140013e58  mov     eax, ebx
0x140013e5a  mov     esi, [r14+10h]
0x140013e5e  mov     r8d, 0FFFFFFFCh
0x140013e64  mov     r12, [r14]
0x140013e67  add     esi, 3
0x140013e6a  and     esi, r8d
0x140013e6d  mov     edi, 0F0h
0x140013e72  lea     edx, [rsi+2Ch]
0x140013e75  add     edx, eax
0x140013e77  cmp     edx, edi
0x140013e79  ja      loc_140014056
0x140013e7f  mov     edi, edx
0x140013e81  mov     dl, dil; EntrySize
0x140013e84  mov     rcx, r15; IoObject
0x140013e87  call    cs:__imp_IoAllocateErrorLogEntry
0x140013e8e  nop     dword ptr [rax+rax+00h]
0x140013e93  mov     rbx, rax
0x140013e96  test    rax, rax
0x140013e99  jz      loc_140013FA3
0x140013e9f  mov     r8d, edi; Size
0x140013ea2  xor     edx, edx; Val
0x140013ea4  mov     rcx, rax; void *
0x140013ea7  call    memset
0x140013eac  mov     word ptr [rbx], 10Fh
0x140013eb1  lea     ecx, [rsi+4]
0x140013eb4  mov     [rbx+2], cx
0x140013eb8  lea     eax, [rsi+2Ch]
0x140013ebb  mov     [rbx+6], ax
0x140013ebf  mov     eax, [r14+18h]
0x140013ec3  mov     [rbx+0Ch], eax
0x140013ec6  movzx   eax, byte ptr [r14+14h]
0x140013ecb  movzx   ecx, byte ptr [r14+16h]
0x140013ed0  shl     ecx, 8
0x140013ed3  or      ecx, eax
0x140013ed5  movzx   eax, byte ptr [r14+15h]
0x140013eda  shl     ecx, 8
0x140013edd  or      ecx, eax
0x140013edf  shl     ecx, 8
0x140013ee2  mov     [rbx+28h], ecx
0x140013ee5  lea     rcx, [rbx+2Ch]; void *
0x140013ee9  mov     eax, [r14+10h]
0x140013eed  mov     rdx, [r14+8]; Src
0x140013ef1  cmp     esi, eax
0x140013ef3  jbe     loc_140013FF9
0x140013ef9  mov     r8d, eax; Size
0x140013efc  call    memmove
0x140013f01  mov     eax, [r14+10h]
0x140013f05  mov     edx, 2Dh ; '-'; Val
0x140013f0a  sub     esi, eax
0x140013f0c  mov     r8d, esi; Size
0x140013f0f  lea     rcx, [rax+2Ch]
0x140013f13  add     rcx, rbx; void *
0x140013f16  call    memset
0x140013f1b  movzx   eax, word ptr [rbx+6]
0x140013f1f  movzx   ebp, word ptr [rbx+2]
0x140013f23  sub     edi, eax
0x140013f25  mov     eax, [r14+18h]
0x140013f29  add     rbp, 28h ; '('
0x140013f2d  add     rbp, rbx
0x140013f30  cmp     eax, 80040099h
0x140013f35  jnz     loc_14001407A
0x140013f3b  mov     r9, [r14+20h]
0x140013f3f  lea     r8, a0xI64x; "0x%I64x"
0x140013f46  movsxd  rdx, edi; cbDest
0x140013f49  mov     rcx, rbp; pszDest
0x140013f4c  call    RtlStringCbPrintfW
0x140013f51  xor     edx, edx
0x140013f53  test    eax, eax
0x140013f55  js      short loc_140013F7D
0x140013f57  inc     word ptr [rbx+4]
0x140013f5b  or      rsi, 0FFFFFFFFFFFFFFFFh
0x140013f5f  mov     rcx, rsi
0x140013f62  inc     rcx
0x140013f65  cmp     [rbp+rcx*2+0], dx
0x140013f6a  jnz     short loc_140013F62
0x140013f6c  lea     eax, ds:2[rcx*2]
0x140013f73  sub     edi, eax
0x140013f75  test    edi, edi
0x140013f77  jg      loc_140014095
0x140013f7d  mov     rcx, rbx; ElEntry
0x140013f80  call    cs:__imp_IoWriteErrorLogEntry
0x140013f87  nop     dword ptr [rax+rax+00h]
0x140013f8c  mov     rcx, cs:WPP_GLOBAL_Control
0x140013f93  lea     rax, WPP_GLOBAL_Control
0x140013f9a  cmp     rcx, rax
0x140013f9d  jnz     loc_1400140C4
0x140013fa3  mov     rdx, r12; Tag
0x140013fa6  mov     rcx, r15; DeviceObject
0x140013fa9  call    ClassReleaseRemoveLock
0x140013fae  mov     rcx, [r14+8]; P
0x140013fb2  test    rcx, rcx
0x140013fb5  jnz     loc_1400140F6
0x140013fbb  test    r12, r12
0x140013fbe  jz      short loc_140013FCF
0x140013fc0  mov     rcx, r12; IoWorkItem
0x140013fc3  call    cs:__imp_IoFreeWorkItem
0x140013fca  nop     dword ptr [rax+rax+00h]
0x140013fcf  xor     edx, edx; Tag
0x140013fd1  mov     rcx, r14; P
0x140013fd4  call    cs:__imp_ExFreePoolWithTag
0x140013fdb  nop     dword ptr [rax+rax+00h]
0x140013fe0  mov     rbx, [rsp+68h+arg_10]
0x140013fe8  add     rsp, 30h
0x140013fec  pop     r15
0x140013fee  pop     r14
0x140013ff0  pop     r13
0x140013ff2  pop     r12
0x140013ff4  pop     rdi
0x140013ff5  pop     rsi
0x140013ff6  pop     rbp
0x140013ff7  retn
0x140013ff9  mov     r8d, esi; Size
0x140013ffc  call    memmove
0x140014001  jmp     loc_140013F1B
0x140014006  mov     eax, 68h ; 'h'
0x14001400b  jmp     loc_140013E5A
0x140014010  mov     rcx, [r13+200h]; DeviceObject
0x140014017  lea     rax, [rsp+68h+BufferLength]
0x14001401c  xor     r9d, r9d; PropertyBuffer
0x14001401f  mov     [rsp+68h+ResultLength], rax; ResultLength
0x140014024  xor     r8d, r8d; BufferLength
0x140014027  lea     edx, [r9+0Bh]; DeviceProperty
0x14001402b  call    cs:__imp_IoGetDeviceProperty
0x140014032  nop     dword ptr [rax+rax+00h]
0x140014037  cmp     eax, 0C0000023h
0x14001403c  jnz     loc_1400402B4
0x140014042  mov     eax, [rsp+68h+BufferLength]
0x140014046  test    eax, eax
0x140014048  jz      loc_1400402B4
0x14001404e  add     eax, 3Ch ; '<'
0x140014051  jmp     loc_140013E5A
0x140014056  test    esi, esi
0x140014058  jz      loc_140013E81
0x14001405e  mov     ecx, edx
0x140014060  sub     rcx, rdi
0x140014063  mov     eax, esi
0x140014065  cmp     rcx, rax
0x140014068  jnb     loc_1400402C2
0x14001406e  sub     esi, edx
0x140014070  add     esi, edi
0x140014072  and     esi, r8d
0x140014075  jmp     loc_140013E81
0x14001407a  cmp     eax, 8004009Bh
0x14001407f  jz      loc_1400402C9
0x140014085  cmp     eax, 0C004009Ah
0x14001408a  jz      loc_140013F3B
0x140014090  jmp     loc_140013F7D
0x140014095  mov     r9d, [r14+28h]
0x140014099  lea     rbp, [rbp+rcx*2+0]
0x14001409e  lea     rcx, [rbp+2]; pszDest
0x1400140a2  movsxd  rdx, edi; cbDest
0x1400140a5  lea     r8, a0123456789abcd+10h; pszFormat
0x1400140ac  call    RtlStringCbPrintfW
0x1400140b1  xor     ecx, ecx
0x1400140b3  test    eax, eax
0x1400140b5  js      loc_140013F7D
0x1400140bb  inc     word ptr [rbx+4]
0x1400140bf  jmp     loc_1400403AC
0x1400140c4  mov     eax, [rcx+2Ch]
0x1400140c7  test    al, 1
0x1400140c9  jz      loc_140013FA3
0x1400140cf  cmp     byte ptr [rcx+29h], 4
0x1400140d3  jb      loc_140013FA3
0x1400140d9  mov     rcx, [rcx+18h]
0x1400140dd  lea     r8, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids
0x1400140e4  mov     edx, 56h ; 'V'
0x1400140e9  mov     r9, r15
0x1400140ec  call    WPP_SF_q
0x1400140f1  jmp     loc_140013FA3
0x1400140f6  xor     edx, edx; Tag
0x1400140f8  call    cs:__imp_ExFreePoolWithTag
0x1400140ff  nop     dword ptr [rax+rax+00h]
0x140014104  jmp     loc_140013FBB
0x1400402b4  mov     eax, 3Ch ; '<'
0x1400402b9  mov     [rsp+68h+BufferLength], ebx
0x1400402bd  jmp     loc_140013E5A
0x1400402c2  mov     esi, ebx
0x1400402c4  jmp     loc_140013E81
0x1400402c9  mov     r9, [r14+20h]
0x1400402cd  lea     r8, a0xI64x; "0x%I64x"
0x1400402d4  movsxd  rdx, edi; cbDest
0x1400402d7  mov     rcx, rbp; pszDest
0x1400402da  call    RtlStringCbPrintfW
0x1400402df  xor     r13d, r13d
0x1400402e2  test    eax, eax
0x1400402e4  js      loc_140013F7D
0x1400402ea  inc     word ptr [rbx+4]
0x1400402ee  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1400402f2  mov     rcx, rsi
0x1400402f5  inc     rcx
0x1400402f8  cmp     [rbp+rcx*2+0], r13w
0x1400402fe  jnz     short loc_1400402F5
0x140040300  mov     r9d, [r14+28h]
0x140040304  lea     eax, ds:2[rcx*2]
0x14004030b  lea     rbp, [rbp+rcx*2+0]
0x140040310  sub     edi, eax
0x140040312  add     rbp, 2
0x140040316  movsxd  rdx, edi; cbDest
0x140040319  mov     rcx, rbp; pszDest
0x14004031c  lea     r8, a0123456789abcd+10h; pszFormat
0x140040323  call    RtlStringCbPrintfW
0x140040328  test    eax, eax
0x14004032a  js      loc_140013F7D
0x140040330  inc     word ptr [rbx+4]
0x140040334  mov     rcx, rsi
0x140040337  inc     rcx
0x14004033a  cmp     [rbp+rcx*2+0], r13w
0x140040340  jnz     short loc_140040337
0x140040342  mov     r9d, [r14+30h]
0x140040346  lea     eax, ds:2[rcx*2]
0x14004034d  sub     edi, eax
0x14004034f  lea     rbp, [rbp+rcx*2+0]
0x140040354  movsxd  rdx, edi; cbDest
0x140040357  lea     r8, a0123456789abcd+10h; pszFormat
0x14004035e  lea     rcx, [rbp+2]; pszDest
0x140040362  call    RtlStringCbPrintfW
0x140040367  test    eax, eax
0x140040369  js      loc_140013F7D
0x14004036f  inc     word ptr [rbx+4]
0x140040373  inc     rsi
0x140040376  cmp     [rbp+rsi*2+2], r13w
0x14004037c  jnz     short loc_140040373
0x14004037e  mov     r9d, [r14+38h]
0x140040382  lea     eax, ds:2[rsi*2]
0x140040389  sub     edi, eax
0x14004038b  lea     rcx, [rbp+4]
0x14004038f  movsxd  rdx, edi; cbDest
0x140040392  lea     rcx, [rcx+rsi*2]; pszDest
0x140040396  lea     r8, a0123456789abcd+10h; pszFormat
0x14004039d  call    RtlStringCbPrintfW
0x1400403a2  test    eax, eax
0x1400403a4  js      loc_140013F7D
0x1400403aa  jmp     short loc_14004041A
0x1400403ac  inc     rsi
0x1400403af  cmp     [rbp+rsi*2+2], cx
0x1400403b4  jnz     short loc_1400403AC
0x1400403b6  mov     r8d, [rsp+68h+BufferLength]; BufferLength
0x1400403bb  lea     eax, ds:2[rsi*2]
0x1400403c2  sub     edi, eax
0x1400403c4  cmp     edi, r8d
0x1400403c7  jl      loc_140013F7D
0x1400403cd  test    r8d, r8d
0x1400403d0  jz      loc_140013F7D
0x1400403d6  mov     [rsp+68h+arg_8], ecx
0x1400403da  lea     rax, [rsp+68h+arg_8]
0x1400403df  mov     rcx, [r13+200h]; DeviceObject
0x1400403e6  lea     r9, [rbp+4]
0x1400403ea  lea     r9, [r9+rsi*2]; PropertyBuffer
0x1400403ee  mov     [rsp+68h+ResultLength], rax; ResultLength
0x1400403f3  mov     edx, 0Bh; DeviceProperty
0x1400403f8  call    cs:__imp_IoGetDeviceProperty
0x1400403ff  nop     dword ptr [rax+rax+00h]
0x140040404  xor     r13d, r13d
0x140040407  test    eax, eax
0x140040409  js      loc_140013F7D
0x14004040f  cmp     [rsp+68h+arg_8], r13d
0x140040414  jbe     loc_140013F7D
0x14004041a  inc     word ptr [rbx+4]
0x14004041e  jmp     loc_140013F7D
```
