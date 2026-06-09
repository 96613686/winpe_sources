# FveFilterCreate

- ea: `0x1400887c0`
- end: `0x1400889df`
- name: `FveFilterCreate`
- size: `543`
- prototype: `__int64 __fastcall(__int64, IRP *)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x140022cd0`
- `0x14002d490`
- `0x14002f388`
- `0x1400887c0`
- `0x1400889e8`
- `0x140088a28`
- `0x140088d8c`
- `0x140088dd0`
- `0x140088e48`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140088962`
- `ntoskrnl!IofCompleteRequest` at `0x140088962`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140088828`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140088828`
- `ntoskrnl!RtlMapGenericMask` at `0x14008883c`
- `ntoskrnl!RtlMapGenericMask` at `0x14008883c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140088945`
- `ntoskrnl!ExFreePoolWithTag` at `0x140088945`

## pseudocode

```c
__int64 __fastcall FveFilterCreate(__int64 a1, IRP *a2)
{
  _QWORD *v2; // r8
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rdx
  __int64 v5; // rbx
  PIO_SECURITY_CONTEXT SecurityContext; // rax
  PFILE_OBJECT FileObject; // rdi
  struct _GENERIC_MAPPING *FileObjectGenericMapping; // rax
  int v9; // esi
  _QWORD *v10; // r14
  _QWORD *i; // rbx
  __int64 (__fastcall **v12)(_QWORD, IRP *, __int64); // rcx
  unsigned int v14; // ebx
  __int64 v15; // rax
  _QWORD *v16; // rbx
  _QWORD *v17; // rdi
  __int64 v18; // [rsp+30h] [rbp-38h] BYREF
  DWORD AccessMask; // [rsp+70h] [rbp+8h] BYREF
  _QWORD *v20; // [rsp+80h] [rbp+18h] BYREF
  PVOID P; // [rsp+88h] [rbp+20h] BYREF

  v2 = *(_QWORD **)(a1 + 64);
  if ( !*v2 )
    return FveTestRwInvalidRequest(a2);
  if ( *(_QWORD *)(v2[1] + 8LL) != a1 )
    return FveFilterSkip();
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  v5 = v2[2];
  AccessMask = 0;
  SecurityContext = CurrentStackLocation->Parameters.Create.SecurityContext;
  P = 0;
  v20 = 0;
  AccessMask = SecurityContext->DesiredAccess;
  FileObject = CurrentStackLocation->FileObject;
  v18 = 0;
  FileObjectGenericMapping = IoGetFileObjectGenericMapping();
  RtlMapGenericMask(&AccessMask, FileObjectGenericMapping);
  if ( v5 )
  {
    if ( FileObject )
    {
      v9 = BlCdoParsePath(v5, (int)FileObject + 88, (unsigned int)&P, (unsigned int)&v20, (__int64)&v18);
      if ( v9 >= 0 )
      {
        v10 = v20;
        for ( i = &v20; *i; i = (_QWORD *)(*i + 8LL) )
        {
          v12 = *(__int64 (__fastcall ***)(_QWORD, IRP *, __int64))(*(_QWORD *)(*i + 16LL) + 160LL);
          if ( v12 )
          {
            if ( *v12 )
            {
              v9 = (*v12)(v10[2], a2, v18);
              if ( v9 != -1073741822 )
              {
                BlCdoNameListRelease(P);
                return (unsigned int)v9;
              }
            }
          }
        }
        if ( *v10 )
        {
          v9 = -1073741772;
        }
        else
        {
          v14 = ((AccessMask & 0x102) != 0 ? 2 : 0) | 1;
          if ( (AccessMask & 0x81) == 0 )
            v14 = (AccessMask & 0x102) != 0 ? 3 : 0;
          v15 = BlDcbRef(v10[2]);
          if ( v15 )
          {
            BlAttachFileObject(v15, FileObject, v14);
            v9 = 0;
          }
          else
          {
            v9 = -1073741823;
          }
        }
      }
    }
    else
    {
      v9 = -1073741823;
    }
  }
  else
  {
    v9 = -1073741811;
  }
  v16 = P;
  if ( P )
  {
    do
    {
      v17 = v16;
      v16 = (_QWORD *)*v16;
      BlDcbDeref(v17[2]);
      ExFreePoolWithTag(v17, 0);
    }
    while ( v16 );
  }
  a2->IoStatus.Information = 0;
  a2->IoStatus.Status = v9;
  IofCompleteRequest(a2, 0);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1400887c0  mov     r11, rsp
0x1400887c3  push    rbp
0x1400887c4  sub     rsp, 60h
0x1400887c8  mov     r8, [rcx+40h]
0x1400887cc  mov     rbp, rdx
0x1400887cf  cmp     qword ptr [r8], 0
0x1400887d3  jz      loc_1400889B2
0x1400887d9  mov     rax, [r8+8]
0x1400887dd  cmp     [rax+8], rcx
0x1400887e1  jnz     loc_1400888E1
0x1400887e7  mov     rdx, [rdx+0B8h]
0x1400887ee  mov     [r11+10h], rbx
0x1400887f2  mov     rbx, [r8+10h]
0x1400887f6  mov     [r11-10h], rsi
0x1400887fa  mov     [r11-18h], rdi
0x1400887fe  mov     [r11-28h], r15
0x140088802  xor     r15d, r15d
0x140088805  mov     [r11+8], r15d
0x140088809  mov     rax, [rdx+8]
0x14008880d  mov     [r11-20h], r14
0x140088811  mov     [r11+20h], r15
0x140088815  mov     [r11+18h], r15
0x140088819  mov     ecx, [rax+10h]
0x14008881c  mov     [rsp+68h+AccessMask], ecx
0x140088820  mov     rdi, [rdx+30h]
0x140088824  mov     [r11-38h], r15
0x140088828  call    cs:__imp_IoGetFileObjectGenericMapping
0x14008882f  nop     dword ptr [rax+rax+00h]
0x140088834  mov     rdx, rax; GenericMapping
0x140088837  lea     rcx, [rsp+68h+AccessMask]; AccessMask
0x14008883c  call    cs:__imp_RtlMapGenericMask
0x140088843  nop     dword ptr [rax+rax+00h]
0x140088848  test    rbx, rbx
0x14008884b  jz      loc_1400889CB
0x140088851  test    rdi, rdi
0x140088854  jz      loc_1400889D5
0x14008885a  lea     rax, [rsp+68h+var_38]
0x14008885f  mov     rcx, rbx
0x140088862  lea     rdx, [rdi+58h]
0x140088866  mov     [rsp+68h+var_48], rax
0x14008886b  lea     r9, [rsp+68h+arg_10]
0x140088873  lea     r8, [rsp+68h+P]
0x14008887b  call    BlCdoParsePath
0x140088880  mov     esi, eax
0x140088882  test    eax, eax
0x140088884  js      loc_140088924
0x14008888a  mov     r14, [rsp+68h+arg_10]
0x140088892  lea     rbx, [rsp+68h+arg_10]
0x14008889a  mov     rax, [rbx]
0x14008889d  test    rax, rax
0x1400888a0  jz      short loc_1400888EB
0x1400888a2  mov     rax, [rax+10h]
0x1400888a6  mov     rcx, [rax+0A0h]
0x1400888ad  test    rcx, rcx
0x1400888b0  jz      short loc_1400888D8
0x1400888b2  mov     rax, [rcx]
0x1400888b5  test    rax, rax
0x1400888b8  jz      short loc_1400888D8
0x1400888ba  mov     r8, [rsp+68h+var_38]
0x1400888bf  mov     rdx, rbp
0x1400888c2  mov     rcx, [r14+10h]
0x1400888c6  call    _guard_dispatch_icall
0x1400888cb  mov     esi, eax
0x1400888cd  cmp     eax, 0C0000002h
0x1400888d2  jnz     loc_1400889A3
0x1400888d8  mov     rbx, [rbx]
0x1400888db  add     rbx, 8
0x1400888df  jmp     short loc_14008889A
0x1400888e1  call    FveFilterSkip
0x1400888e6  jmp     loc_140088989
0x1400888eb  cmp     [r14], r15
0x1400888ee  jnz     loc_1400889C1
0x1400888f4  mov     eax, [rsp+68h+AccessMask]
0x1400888f8  mov     rcx, [r14+10h]
0x1400888fc  and     eax, 102h
0x140088901  neg     eax
0x140088903  sbb     edx, edx
0x140088905  and     edx, 3
0x140088908  mov     ebx, edx
0x14008890a  or      ebx, 1
0x14008890d  test    byte ptr [rsp+68h+AccessMask], 81h
0x140088912  cmovz   ebx, edx
0x140088915  call    BlDcbRef
0x14008891a  test    rax, rax
0x14008891d  jnz     short loc_140088990
0x14008891f  mov     esi, 0C0000001h
0x140088924  mov     rbx, [rsp+68h+P]
0x14008892c  test    rbx, rbx
0x14008892f  jz      short loc_140088956
0x140088931  mov     rdi, rbx
0x140088934  mov     rbx, [rbx]
0x140088937  mov     rcx, [rdi+10h]
0x14008893b  call    BlDcbDeref
0x140088940  xor     edx, edx; Tag
0x140088942  mov     rcx, rdi; P
0x140088945  call    cs:__imp_ExFreePoolWithTag
0x14008894c  nop     dword ptr [rax+rax+00h]
0x140088951  test    rbx, rbx
0x140088954  jnz     short loc_140088931
0x140088956  xor     edx, edx; PriorityBoost
0x140088958  mov     [rbp+38h], r15
0x14008895c  mov     rcx, rbp; Irp
0x14008895f  mov     [rbp+30h], esi
0x140088962  call    cs:__imp_IofCompleteRequest
0x140088969  nop     dword ptr [rax+rax+00h]
0x14008896e  mov     r15, [rsp+68h+var_28]
0x140088973  mov     eax, esi
0x140088975  mov     rsi, [rsp+68h+var_10]
0x14008897a  mov     r14, [rsp+68h+var_20]
0x14008897f  mov     rdi, [rsp+68h+var_18]
0x140088984  mov     rbx, [rsp+68h+arg_8]
0x140088989  add     rsp, 60h
0x14008898d  pop     rbp
0x14008898e  retn
0x140088990  mov     r8d, ebx
0x140088993  mov     rdx, rdi
0x140088996  mov     rcx, rax
0x140088999  call    BlAttachFileObject
0x14008899e  mov     esi, r15d
0x1400889a1  jmp     short loc_140088924
0x1400889a3  mov     rcx, [rsp+68h+P]; P
0x1400889ab  call    BlCdoNameListRelease
0x1400889b0  jmp     short loc_14008896E
0x1400889b2  mov     rcx, rbp
0x1400889b5  call    FveTestRwInvalidRequest
0x1400889ba  add     rsp, 60h
0x1400889be  pop     rbp
0x1400889bf  retn
0x1400889c1  mov     esi, 0C0000034h
0x1400889c6  jmp     loc_140088924
0x1400889cb  mov     esi, 0C000000Dh
0x1400889d0  jmp     loc_140088924
0x1400889d5  mov     esi, 0C0000001h
0x1400889da  jmp     loc_140088924
```
