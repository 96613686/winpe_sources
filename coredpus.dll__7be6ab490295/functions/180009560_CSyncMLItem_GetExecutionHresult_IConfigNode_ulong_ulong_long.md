# CSyncMLItem::GetExecutionHresult(IConfigNode *,ulong,ulong,long *)

- ea: `0x180009560`
- end: `0x180009755`
- name: `?GetExecutionHresult@CSyncMLItem@@AEBAJPEAUIConfigNode@@KKPEAJ@Z`
- size: `501`
- prototype: `__int64 __fastcall(CSyncMLItem *__hidden this, struct IConfigNode *, unsigned int, unsigned int, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180003b60`

## callees

- `0x180009560`
- `0x180014330`
- `0x180030010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180009719`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180009719`

## pseudocode

```c
__int64 __fastcall CSyncMLItem::GetExecutionHresult(
        CSyncMLItem *this,
        struct IConfigNode *a2,
        unsigned int a3,
        unsigned int a4,
        int *a5)
{
  int v7; // edi
  int v8; // ebx
  int v10; // [rsp+38h] [rbp-31h] BYREF
  int v11; // [rsp+3Ch] [rbp-2Dh] BYREF
  __int64 v12; // [rsp+40h] [rbp-29h] BYREF
  _DWORD v13[2]; // [rsp+48h] [rbp-21h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+50h] [rbp-19h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+60h] [rbp-9h] BYREF
  char *v16; // [rsp+70h] [rbp+7h]
  int v17; // [rsp+78h] [rbp+Fh]
  int v18; // [rsp+7Ch] [rbp+13h]
  _DWORD *v19; // [rsp+80h] [rbp+17h]
  __int64 v20; // [rsp+88h] [rbp+1Fh]

  v11 = 0;
  v12 = 0;
  v10 = 0;
  if ( !a2 )
    goto LABEL_12;
  v7 = (*(__int64 (__fastcall **)(struct IConfigNode *, __int64 *))(*(_QWORD *)a2 + 152LL))(a2, &v12);
  if ( v7 < 0 )
    goto LABEL_13;
  if ( a3 )
  {
    v7 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v12 + 32LL))(v12, a3);
    if ( v7 < 0 )
      goto LABEL_13;
  }
  v8 = 0;
  if ( !a4 )
  {
LABEL_12:
    v7 = 1;
    goto LABEL_13;
  }
  while ( 1 )
  {
    v7 = (*(__int64 (__fastcall **)(__int64, __int64, int *, int *))(*(_QWORD *)v12 + 24LL))(v12, 1, &v11, &v10);
    if ( v7 < 0 )
      break;
    if ( v10 != 1 )
    {
      v7 = -2147418113;
      break;
    }
    if ( v11 < 0 || (unsigned int)v11 >= 2 && v11 != 100663303 )
    {
      *a5 = v11;
      v7 = 0;
      break;
    }
    if ( ++v8 >= a4 )
      goto LABEL_12;
  }
LABEL_13:
  if ( v12 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    v12 = 0;
  }
  if ( (unsigned int)dword_18003E048 > 5 )
  {
    v13[0] = v7;
    v19 = v13;
    *(_DWORD *)&EventDescriptor.Level = 5;
    UserData.Ptr = (ULONGLONG)off_18003E050;
    v20 = 4;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 0;
    UserData.Size = (unsigned __int16)*off_18003E050;
    v16 = byte_1800363F1;
    UserData.Reserved = 2;
    v17 = 32;
    v18 = 1;
    v13[1] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180009560  mov     r11, rsp
0x180009563  push    rbp
0x180009564  push    rdi
0x180009565  push    r15
0x180009567  lea     rbp, [r11-57h]
0x18000956b  sub     rsp, 0A0h
0x180009572  mov     rax, cs:__security_cookie
0x180009579  xor     rax, rsp
0x18000957c  mov     [rbp+4Fh+var_28], rax
0x180009580  xor     r15d, r15d
0x180009583  mov     [r11+8], rbx
0x180009587  mov     [r11-20h], rsi
0x18000958b  mov     ebx, r8d
0x18000958e  mov     [r11-28h], r14
0x180009592  mov     esi, r9d
0x180009595  mov     r14, [rbp+4Fh+arg_20]
0x180009599  mov     r8, rdx
0x18000959c  mov     [rbp+4Fh+var_7C], r15d
0x1800095a0  mov     [rbp+4Fh+var_78], r15
0x1800095a4  mov     [rbp+4Fh+var_80], r15d
0x1800095a8  test    rdx, rdx
0x1800095ab  jz      loc_180009643
0x1800095b1  mov     rax, [rdx]
0x1800095b4  mov     rcx, r8
0x1800095b7  lea     rdx, [rbp+4Fh+var_78]
0x1800095bb  mov     rax, [rax+98h]
0x1800095c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800095c7  mov     edi, eax
0x1800095c9  test    eax, eax
0x1800095cb  js      short loc_180009648
0x1800095cd  test    ebx, ebx
0x1800095cf  jz      short loc_1800095E9
0x1800095d1  mov     rcx, [rbp+4Fh+var_78]
0x1800095d5  mov     edx, ebx
0x1800095d7  mov     rax, [rcx]
0x1800095da  mov     rax, [rax+20h]
0x1800095de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800095e3  mov     edi, eax
0x1800095e5  test    eax, eax
0x1800095e7  js      short loc_180009648
0x1800095e9  mov     ebx, r15d
0x1800095ec  test    esi, esi
0x1800095ee  jz      short loc_180009643
0x1800095f0  mov     rcx, [rbp+4Fh+var_78]
0x1800095f4  lea     r9, [rbp+4Fh+var_80]
0x1800095f8  lea     r8, [rbp+4Fh+var_7C]
0x1800095fc  mov     edx, 1
0x180009601  mov     rax, [rcx]
0x180009604  mov     rax, [rax+18h]
0x180009608  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000960d  mov     edi, eax
0x18000960f  test    eax, eax
0x180009611  js      short loc_180009648
0x180009613  cmp     [rbp+4Fh+var_80], 1
0x180009617  jnz     loc_18000974B
0x18000961d  mov     edx, [rbp+4Fh+var_7C]
0x180009620  test    edx, edx
0x180009622  js      loc_180009740
0x180009628  mov     ecx, edx
0x18000962a  jz      short loc_18000963D
0x18000962c  sub     ecx, 1
0x18000962f  jz      short loc_18000963D
0x180009631  cmp     ecx, 6000006h
0x180009637  jnz     loc_180009740
0x18000963d  inc     ebx
0x18000963f  cmp     ebx, esi
0x180009641  jb      short loc_1800095F0
0x180009643  mov     edi, 1
0x180009648  mov     rcx, [rbp+4Fh+var_78]
0x18000964c  mov     r14, [rsp+0B0h+var_20]
0x180009654  mov     rsi, [rsp+98h]
0x18000965c  mov     rbx, [rsp+0B0h+arg_0]
0x180009664  test    rcx, rcx
0x180009667  jz      short loc_180009679
0x180009669  mov     rax, [rcx]
0x18000966c  mov     rax, [rax+10h]
0x180009670  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009675  mov     [rbp+4Fh+var_78], r15
0x180009679  mov     eax, cs:dword_18003E048
0x18000967f  cmp     eax, 5
0x180009682  jbe     loc_180009725
0x180009688  lea     rax, [rbp+4Fh+var_70]
0x18000968c  mov     [rbp+4Fh+var_70], edi
0x18000968f  mov     [rbp+4Fh+var_38], rax
0x180009693  lea     rcx, _TraceLoggingMetadata
0x18000969a  movzx   eax, cs:word_1800363E7
0x1800096a1  lea     rdx, [rbp+4Fh+EventDescriptor]; EventDescriptor
0x1800096a5  mov     dword ptr [rbp+4Fh+EventDescriptor.Level], eax
0x1800096a8  xor     r9d, r9d; RelatedActivityId
0x1800096ab  mov     rax, cs:off_18003E050
0x1800096b2  xor     r8d, r8d; ActivityId
0x1800096b5  mov     [rbp+4Fh+UserData.Ptr], rax
0x1800096b9  mov     [rbp+4Fh+var_30], 4
0x1800096c1  mov     dword ptr [rbp+4Fh+EventDescriptor.Id], 0B000000h
0x1800096c8  mov     [rbp+4Fh+EventDescriptor.Keyword], r15
0x1800096cc  movzx   eax, word ptr [rax]
0x1800096cf  mov     [rbp+4Fh+UserData.Size], eax
0x1800096d2  lea     rax, byte_1800363F1
0x1800096d9  mov     [rbp+4Fh+var_48], rax
0x1800096dd  lea     rax, _TraceLoggingMetadataEnd
0x1800096e4  sub     eax, ecx
0x1800096e6  mov     dword ptr [rbp+4Fh+UserData.0Ch], 2
0x1800096ed  mov     [rbp+4Fh+var_40], 20h ; ' '
0x1800096f4  mov     [rbp+4Fh+var_3C], 1
0x1800096fb  mov     [rbp+4Fh+var_6C], eax
0x1800096fe  mov     eax, [rbp+4Fh+var_6C]
0x180009701  mov     rcx, cs:RegHandle; RegHandle
0x180009708  lea     rax, [rbp+4Fh+UserData]
0x18000970c  mov     [rsp+28h], rax; UserData
0x180009711  mov     [rsp+0B0h+UserDataCount], 3; UserDataCount
0x180009719  call    cs:__imp_EventWriteTransfer
0x180009720  nop     dword ptr [rax+rax+00h]
0x180009725  mov     eax, edi
0x180009727  mov     rcx, [rbp+4Fh+var_28]
0x18000972b  xor     rcx, rsp; StackCookie
0x18000972e  call    __security_check_cookie
0x180009733  add     rsp, 0A0h
0x18000973a  pop     r15
0x18000973c  pop     rdi
0x18000973d  pop     rbp
0x18000973e  retn
0x180009740  mov     [r14], edx
0x180009743  mov     edi, r15d
0x180009746  jmp     loc_180009648
0x18000974b  mov     edi, 8000FFFFh
0x180009750  jmp     loc_180009648
```
