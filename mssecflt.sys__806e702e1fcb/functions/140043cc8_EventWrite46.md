# EventWrite46

- ea: `0x140043cc8`
- end: `0x140043e15`
- name: `EventWrite46`
- size: `333`
- prototype: `__int64 __fastcall(int, int, int, int, char, wchar_t *Str, wchar_t *, char)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14004162c`

## callees

- `0x140008714`
- `0x14000876c`
- `0x14001008c`
- `0x140043cc8`

## import_xrefs

- `ntoskrnl!EtwWrite` at `0x140043df1`
- `ntoskrnl!EtwWrite` at `0x140043df1`

## pseudocode

```c
__int64 EventWrite46(__int64 a1, int a2, __int64 a3, __int64 a4, char a5, wchar_t *Str, wchar_t *a7, ...)
{
  PSLIST_ENTRY EtwDescriptorBuffer; // rax
  PSLIST_ENTRY UserData; // rdi
  const wchar_t *v10; // rbx
  int v11; // esi
  int v12; // ecx
  const WCHAR *v13; // rbp
  const WCHAR *v14; // rax
  const wchar_t *v15; // rbx
  bool v16; // zf
  int v17; // eax
  unsigned int v18; // ebx
  __int64 v19; // [rsp+60h] [rbp+8h] BYREF
  int v20; // [rsp+68h] [rbp+10h] BYREF
  __int64 v21; // [rsp+70h] [rbp+18h] BYREF
  __int64 v22; // [rsp+78h] [rbp+20h] BYREF
  va_list va; // [rsp+98h] [rbp+40h] BYREF

  va_start(va, a7);
  v22 = a4;
  v21 = a3;
  v20 = a2;
  v19 = a1;
  EtwDescriptorBuffer = SecGetEtwDescriptorBuffer(8u);
  UserData = EtwDescriptorBuffer;
  if ( !EtwDescriptorBuffer )
    return 3221225626LL;
  v10 = Str;
  EtwDescriptorBuffer->Next = (struct _SLIST_ENTRY *)&v19;
  EtwDescriptorBuffer[1].Next = (struct _SLIST_ENTRY *)&v20;
  EtwDescriptorBuffer[2].Next = (struct _SLIST_ENTRY *)&v21;
  EtwDescriptorBuffer[3].Next = (struct _SLIST_ENTRY *)&v22;
  EtwDescriptorBuffer[4].Next = (struct _SLIST_ENTRY *)&a5;
  v11 = 2;
  *((_QWORD *)&EtwDescriptorBuffer->Next + 1) = 8;
  *((_QWORD *)&EtwDescriptorBuffer[1].Next + 1) = 4;
  *((_QWORD *)&EtwDescriptorBuffer[2].Next + 1) = 8;
  *((_QWORD *)&EtwDescriptorBuffer[3].Next + 1) = 8;
  *((_QWORD *)&EtwDescriptorBuffer[4].Next + 1) = 4;
  if ( v10 )
    v12 = 2 * wcslen_0(v10) + 2;
  else
    v12 = 2;
  *((_DWORD *)&UserData[5].Next + 2) = v12;
  v13 = &SourceString;
  *((_DWORD *)&UserData[5].Next + 3) = 0;
  v14 = &SourceString;
  if ( v10 )
    v14 = v10;
  v15 = a7;
  UserData[5].Next = (struct _SLIST_ENTRY *)v14;
  v16 = v15 == 0;
  if ( v15 )
  {
    v17 = wcslen_0(v15);
    v16 = v15 == 0;
    v11 = 2 * v17 + 2;
  }
  if ( !v16 )
    v13 = v15;
  *((_DWORD *)&UserData[6].Next + 2) = v11;
  UserData[6].Next = (struct _SLIST_ENTRY *)v13;
  UserData[7].Next = (struct _SLIST_ENTRY *)va;
  *((_DWORD *)&UserData[6].Next + 3) = 0;
  *((_QWORD *)&UserData[7].Next + 1) = 4;
  v18 = EtwWrite(Microsoft_Windows_SECHandle, &Event46, 0, 8u, (PEVENT_DATA_DESCRIPTOR)UserData);
  SecReleaseEtwDescriptorBuffer(UserData);
  return v18;
}

```

## disassembly

```asm
0x140043cc8  mov     rax, rsp
0x140043ccb  mov     [rax+20h], r9
0x140043ccf  mov     [rax+18h], r8
0x140043cd3  mov     [rax+10h], edx
0x140043cd6  mov     [rax+8], rcx
0x140043cda  push    rbx
0x140043cdb  push    rbp
0x140043cdc  push    rsi
0x140043cdd  push    rdi
0x140043cde  push    r15
0x140043ce0  sub     rsp, 30h
0x140043ce4  mov     r15d, 8
0x140043cea  mov     ecx, r15d
0x140043ced  call    SecGetEtwDescriptorBuffer
0x140043cf2  mov     rdi, rax
0x140043cf5  test    rax, rax
0x140043cf8  jnz     short loc_140043D04
0x140043cfa  mov     eax, 0C000009Ah
0x140043cff  jmp     loc_140043E09
0x140043d04  mov     rbx, [rsp+58h+Str]
0x140043d0c  lea     rax, [rsp+58h+arg_0]
0x140043d11  mov     [rdi], rax
0x140043d14  lea     rax, [rsp+58h+arg_8]
0x140043d19  mov     [rdi+10h], rax
0x140043d1d  lea     rax, [rsp+58h+arg_10]
0x140043d22  mov     [rdi+20h], rax
0x140043d26  lea     rax, [rsp+58h+arg_18]
0x140043d2b  mov     [rdi+30h], rax
0x140043d2f  lea     rax, [rsp+58h+arg_20]
0x140043d37  mov     [rdi+40h], rax
0x140043d3b  mov     esi, 2
0x140043d40  mov     [rdi+8], r15
0x140043d44  mov     qword ptr [rdi+18h], 4
0x140043d4c  mov     [rdi+28h], r15
0x140043d50  mov     [rdi+38h], r15
0x140043d54  mov     qword ptr [rdi+48h], 4
0x140043d5c  test    rbx, rbx
0x140043d5f  jz      short loc_140043D72
0x140043d61  mov     rcx, rbx; Str
0x140043d64  call    wcslen_0
0x140043d69  lea     ecx, ds:2[rax*2]
0x140043d70  jmp     short loc_140043D74
0x140043d72  mov     ecx, esi
0x140043d74  test    rbx, rbx
0x140043d77  mov     [rdi+58h], ecx
0x140043d7a  lea     rbp, SourceString
0x140043d81  mov     dword ptr [rdi+5Ch], 0
0x140043d88  mov     rax, rbp
0x140043d8b  cmovnz  rax, rbx
0x140043d8f  mov     rbx, [rsp+58h+arg_30]
0x140043d97  mov     [rdi+50h], rax
0x140043d9b  test    rbx, rbx
0x140043d9e  jz      short loc_140043DB2
0x140043da0  mov     rcx, rbx; Str
0x140043da3  call    wcslen_0
0x140043da8  test    rbx, rbx
0x140043dab  lea     esi, ds:2[rax*2]
0x140043db2  cmovnz  rbp, rbx
0x140043db6  mov     [rdi+68h], esi
0x140043db9  lea     rax, [rsp+58h+arg_38]
0x140043dc1  mov     [rdi+60h], rbp
0x140043dc5  mov     [rdi+70h], rax
0x140043dc9  lea     rdx, Event46; EventDescriptor
0x140043dd0  mov     dword ptr [rdi+6Ch], 0
0x140043dd7  mov     r9d, r15d; UserDataCount
0x140043dda  mov     qword ptr [rdi+78h], 4
0x140043de2  xor     r8d, r8d; ActivityId
0x140043de5  mov     rcx, cs:Microsoft_Windows_SECHandle; RegHandle
0x140043dec  mov     [rsp+58h+UserData], rdi; UserData
0x140043df1  call    cs:__imp_EtwWrite
0x140043df8  nop     dword ptr [rax+rax+00h]
0x140043dfd  mov     rcx, rdi; ListEntry
0x140043e00  mov     ebx, eax
0x140043e02  call    SecReleaseEtwDescriptorBuffer
0x140043e07  mov     eax, ebx
0x140043e09  add     rsp, 30h
0x140043e0d  pop     r15
0x140043e0f  pop     rdi
0x140043e10  pop     rsi
0x140043e11  pop     rbp
0x140043e12  pop     rbx
0x140043e13  retn
```
