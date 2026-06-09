# LuafvLogExclusion

- ea: `0x140018530`
- end: `0x140018606`
- name: `LuafvLogExclusion`
- size: `214`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x140018f70`
- `0x140025350`
- `0x1400258a0`

## callees

- `0x140005f30`
- `0x140018530`
- `0x14001897c`

## pseudocode

```c
__int64 __fastcall LuafvLogExclusion(struct _FLT_CALLBACK_DATA *a1, UNICODE_STRING *a2, __int64 a3, int a4)
{
  PFLT_IO_PARAMETER_BLOCK Iopb; // rax
  ULONG *p_Options; // rcx
  _DWORD *v7; // rax
  _DWORD v9[4]; // [rsp+40h] [rbp-C0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v10; // [rsp+50h] [rbp-B0h] BYREF
  ULONG *v11; // [rsp+C0h] [rbp-40h]
  __int64 v12; // [rsp+C8h] [rbp-38h]
  _DWORD *v13; // [rsp+D0h] [rbp-30h]
  __int64 v14; // [rsp+D8h] [rbp-28h]
  UCHAR *p_MajorFunction; // [rsp+E0h] [rbp-20h]
  __int64 v16; // [rsp+E8h] [rbp-18h]
  int *v17; // [rsp+F0h] [rbp-10h]
  __int64 v18; // [rsp+F8h] [rbp-8h]
  int v19; // [rsp+138h] [rbp+38h] BYREF

  v19 = a4;
  v18 = 4;
  v17 = &v19;
  Iopb = a1->Iopb;
  v9[0] = 0;
  v16 = 1;
  p_MajorFunction = &Iopb->MajorFunction;
  if ( a3 )
  {
    p_Options = (ULONG *)(a3 + 40);
    v7 = (_DWORD *)(a3 + 44);
  }
  else
  {
    if ( Iopb->MajorFunction )
    {
      v11 = v9;
      v7 = v9;
      goto LABEL_4;
    }
    p_Options = &Iopb->Parameters.Create.Options;
    v7 = (_DWORD *)(Iopb->Parameters.WMI.ProviderId + 16);
  }
  v11 = p_Options;
LABEL_4:
  v13 = v7;
  v14 = 4;
  v12 = 4;
  return LuafvLogFileEvent(a1, a2, 0, 0, &LuafvExclusionEvent, &v10, 0xBu);
}

```

## disassembly

```asm
0x140018530  mov     [rsp-8+arg_18], r9d
0x140018535  push    rbp
0x140018536  lea     rbp, [rsp-10h]
0x14001853b  sub     rsp, 110h
0x140018542  mov     rax, cs:__security_cookie
0x140018549  xor     rax, rsp
0x14001854c  mov     [rbp+10h+var_10], rax
0x140018550  lea     rax, [rbp+10h+arg_18]
0x140018554  mov     [rbp+10h+var_18], 4
0x14001855c  xor     r9d, r9d; int
0x14001855f  mov     [rbp+10h+var_20], rax
0x140018563  mov     rax, [rcx+10h]
0x140018567  mov     r10, rcx
0x14001856a  mov     [rsp+110h+var_D0], r9d
0x14001856f  mov     [rbp+10h+var_28], 1
0x140018577  lea     rcx, [rax+4]
0x14001857b  mov     [rbp+10h+var_30], rcx
0x14001857f  test    r8, r8
0x140018582  jz      short loc_1400185E3
0x140018584  lea     rcx, [r8+28h]
0x140018588  lea     rax, [r8+2Ch]
0x14001858c  mov     [rbp+10h+var_50], rcx
0x140018590  mov     [rbp+10h+var_40], rax
0x140018594  xor     r8d, r8d; int
0x140018597  lea     rax, [rsp+110h+var_C0]
0x14001859c  mov     [rsp+110h+UserDataCount], 0Bh; UserDataCount
0x1400185a4  mov     [rsp+110h+var_E8], rax; PEVENT_DATA_DESCRIPTOR
0x1400185a9  mov     rcx, r10; int
0x1400185ac  lea     rax, LuafvExclusionEvent
0x1400185b3  mov     [rbp+10h+var_38], 4
0x1400185bb  mov     [rsp+110h+EventDescriptor], rax; EventDescriptor
0x1400185c0  mov     [rbp+10h+var_48], 4
0x1400185c8  call    LuafvLogFileEvent
0x1400185cd  mov     rcx, [rbp+10h+var_10]
0x1400185d1  xor     rcx, rsp; StackCookie
0x1400185d4  call    __security_check_cookie
0x1400185d9  add     rsp, 110h
0x1400185e0  pop     rbp
0x1400185e1  retn
0x1400185e3  cmp     [rcx], r9b
0x1400185e6  jz      short loc_1400185F8
0x1400185e8  lea     rax, [rsp+110h+var_D0]
0x1400185ed  mov     [rbp+10h+var_50], rax
0x1400185f1  lea     rax, [rsp+110h+var_D0]
0x1400185f6  jmp     short loc_140018590
0x1400185f8  lea     rcx, [rax+20h]
0x1400185fc  mov     rax, [rax+18h]
0x140018600  add     rax, 10h
0x140018604  jmp     short loc_14001858C
```
