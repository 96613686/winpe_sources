# FveFilterCreate

- ea: `0x140086720`
- end: `0x14008693f`
- name: `FveFilterCreate`
- size: `543`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x1400219a0`
- `0x14002c490`
- `0x14002e388`
- `0x140086720`
- `0x140086948`
- `0x140086988`
- `0x140086cec`
- `0x140086d30`
- `0x140086da8`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x1400868c2`
- `ntoskrnl!IofCompleteRequest` at `0x1400868c2`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140086788`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140086788`
- `ntoskrnl!RtlMapGenericMask` at `0x14008679c`
- `ntoskrnl!RtlMapGenericMask` at `0x14008679c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400868a5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400868a5`

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
  __int64 v10; // r8
  _QWORD *v11; // r14
  _QWORD *i; // rbx
  __int64 (__fastcall **v13)(_QWORD, IRP *, __int64); // rcx
  unsigned int v15; // ebx
  __int64 v16; // rax
  _QWORD *v17; // rbx
  _QWORD *v18; // rdi
  __int64 v19; // [rsp+30h] [rbp-38h] BYREF
  DWORD AccessMask; // [rsp+70h] [rbp+8h] BYREF
  _QWORD *v21; // [rsp+80h] [rbp+18h] BYREF
  PVOID P; // [rsp+88h] [rbp+20h] BYREF

  v2 = *(_QWORD **)(a1 + 64);
  if ( !*v2 )
    return FveTestRwInvalidRequest(a2);
  if ( *(_QWORD *)(v2[1] + 8LL) != a1 )
    return FveFilterSkip(a1, a2);
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  v5 = v2[2];
  AccessMask = 0;
  SecurityContext = CurrentStackLocation->Parameters.Create.SecurityContext;
  P = 0;
  v21 = 0;
  AccessMask = SecurityContext->DesiredAccess;
  FileObject = CurrentStackLocation->FileObject;
  v19 = 0;
  FileObjectGenericMapping = IoGetFileObjectGenericMapping();
  RtlMapGenericMask(&AccessMask, FileObjectGenericMapping);
  if ( v5 )
  {
    if ( FileObject )
    {
      v9 = BlCdoParsePath(v5, (int)FileObject + 88, (unsigned int)&P, (unsigned int)&v21, (__int64)&v19);
      if ( v9 >= 0 )
      {
        v11 = v21;
        for ( i = &v21; *i; i = (_QWORD *)(*i + 8LL) )
        {
          v13 = *(__int64 (__fastcall ***)(_QWORD, IRP *, __int64))(*(_QWORD *)(*i + 16LL) + 160LL);
          if ( v13 )
          {
            if ( *v13 )
            {
              v9 = (*v13)(v11[2], a2, v19);
              if ( v9 != -1073741822 )
              {
                BlCdoNameListRelease(P);
                return (unsigned int)v9;
              }
            }
          }
        }
        if ( *v11 )
        {
          v9 = -1073741772;
        }
        else
        {
          v15 = ((AccessMask & 0x102) != 0 ? 2 : 0) | 1;
          if ( (AccessMask & 0x81) == 0 )
            v15 = (AccessMask & 0x102) != 0 ? 3 : 0;
          v16 = BlDcbRef(v11[2], (AccessMask & 0x102) != 0 ? 3 : 0, v10);
          if ( v16 )
          {
            BlAttachFileObject(v16, FileObject, v15);
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
  v17 = P;
  if ( P )
  {
    do
    {
      v18 = v17;
      v17 = (_QWORD *)*v17;
      BlDcbDeref(v18[2]);
      ExFreePoolWithTag(v18, 0);
    }
    while ( v17 );
  }
  a2->IoStatus.Information = 0;
  a2->IoStatus.Status = v9;
  IofCompleteRequest(a2, 0);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140086720  mov     r11, rsp
0x140086723  push    rbp
0x140086724  sub     rsp, 60h
0x140086728  mov     r8, [rcx+40h]
0x14008672c  mov     rbp, rdx
0x14008672f  cmp     qword ptr [r8], 0
0x140086733  jz      loc_140086912
0x140086739  mov     rax, [r8+8]
0x14008673d  cmp     [rax+8], rcx
0x140086741  jnz     loc_140086841
0x140086747  mov     rdx, [rdx+0B8h]
0x14008674e  mov     [r11+10h], rbx
0x140086752  mov     rbx, [r8+10h]
0x140086756  mov     [r11-10h], rsi
0x14008675a  mov     [r11-18h], rdi
0x14008675e  mov     [r11-28h], r15
0x140086762  xor     r15d, r15d
0x140086765  mov     [r11+8], r15d
0x140086769  mov     rax, [rdx+8]
0x14008676d  mov     [r11-20h], r14
0x140086771  mov     [r11+20h], r15
0x140086775  mov     [r11+18h], r15
0x140086779  mov     ecx, [rax+10h]
0x14008677c  mov     [rsp+68h+AccessMask], ecx
0x140086780  mov     rdi, [rdx+30h]
0x140086784  mov     [r11-38h], r15
0x140086788  call    cs:__imp_IoGetFileObjectGenericMapping
0x14008678f  nop     dword ptr [rax+rax+00h]
0x140086794  mov     rdx, rax; GenericMapping
0x140086797  lea     rcx, [rsp+68h+AccessMask]; AccessMask
0x14008679c  call    cs:__imp_RtlMapGenericMask
0x1400867a3  nop     dword ptr [rax+rax+00h]
0x1400867a8  test    rbx, rbx
0x1400867ab  jz      loc_14008692B
0x1400867b1  test    rdi, rdi
0x1400867b4  jz      loc_140086935
0x1400867ba  lea     rax, [rsp+68h+var_38]
0x1400867bf  mov     rcx, rbx
0x1400867c2  lea     rdx, [rdi+58h]
0x1400867c6  mov     [rsp+68h+var_48], rax
0x1400867cb  lea     r9, [rsp+68h+arg_10]
0x1400867d3  lea     r8, [rsp+68h+P]
0x1400867db  call    BlCdoParsePath
0x1400867e0  mov     esi, eax
0x1400867e2  test    eax, eax
0x1400867e4  js      loc_140086884
0x1400867ea  mov     r14, [rsp+68h+arg_10]
0x1400867f2  lea     rbx, [rsp+68h+arg_10]
0x1400867fa  mov     rax, [rbx]
0x1400867fd  test    rax, rax
0x140086800  jz      short loc_14008684B
0x140086802  mov     rax, [rax+10h]
0x140086806  mov     rcx, [rax+0A0h]
0x14008680d  test    rcx, rcx
0x140086810  jz      short loc_140086838
0x140086812  mov     rax, [rcx]
0x140086815  test    rax, rax
0x140086818  jz      short loc_140086838
0x14008681a  mov     r8, [rsp+68h+var_38]
0x14008681f  mov     rdx, rbp
0x140086822  mov     rcx, [r14+10h]
0x140086826  call    _guard_dispatch_icall
0x14008682b  mov     esi, eax
0x14008682d  cmp     eax, 0C0000002h
0x140086832  jnz     loc_140086903
0x140086838  mov     rbx, [rbx]
0x14008683b  add     rbx, 8
0x14008683f  jmp     short loc_1400867FA
0x140086841  call    FveFilterSkip
0x140086846  jmp     loc_1400868E9
0x14008684b  cmp     [r14], r15
0x14008684e  jnz     loc_140086921
0x140086854  mov     eax, [rsp+68h+AccessMask]
0x140086858  mov     rcx, [r14+10h]
0x14008685c  and     eax, 102h
0x140086861  neg     eax
0x140086863  sbb     edx, edx
0x140086865  and     edx, 3
0x140086868  mov     ebx, edx
0x14008686a  or      ebx, 1
0x14008686d  test    byte ptr [rsp+68h+AccessMask], 81h
0x140086872  cmovz   ebx, edx
0x140086875  call    BlDcbRef
0x14008687a  test    rax, rax
0x14008687d  jnz     short loc_1400868F0
0x14008687f  mov     esi, 0C0000001h
0x140086884  mov     rbx, [rsp+68h+P]
0x14008688c  test    rbx, rbx
0x14008688f  jz      short loc_1400868B6
0x140086891  mov     rdi, rbx
0x140086894  mov     rbx, [rbx]
0x140086897  mov     rcx, [rdi+10h]
0x14008689b  call    BlDcbDeref
0x1400868a0  xor     edx, edx; Tag
0x1400868a2  mov     rcx, rdi; P
0x1400868a5  call    cs:__imp_ExFreePoolWithTag
0x1400868ac  nop     dword ptr [rax+rax+00h]
0x1400868b1  test    rbx, rbx
0x1400868b4  jnz     short loc_140086891
0x1400868b6  xor     edx, edx; PriorityBoost
0x1400868b8  mov     [rbp+38h], r15
0x1400868bc  mov     rcx, rbp; Irp
0x1400868bf  mov     [rbp+30h], esi
0x1400868c2  call    cs:__imp_IofCompleteRequest
0x1400868c9  nop     dword ptr [rax+rax+00h]
0x1400868ce  mov     r15, [rsp+68h+var_28]
0x1400868d3  mov     eax, esi
0x1400868d5  mov     rsi, [rsp+68h+var_10]
0x1400868da  mov     r14, [rsp+68h+var_20]
0x1400868df  mov     rdi, [rsp+68h+var_18]
0x1400868e4  mov     rbx, [rsp+68h+arg_8]
0x1400868e9  add     rsp, 60h
0x1400868ed  pop     rbp
0x1400868ee  retn
0x1400868f0  mov     r8d, ebx
0x1400868f3  mov     rdx, rdi
0x1400868f6  mov     rcx, rax
0x1400868f9  call    BlAttachFileObject
0x1400868fe  mov     esi, r15d
0x140086901  jmp     short loc_140086884
0x140086903  mov     rcx, [rsp+68h+P]; P
0x14008690b  call    BlCdoNameListRelease
0x140086910  jmp     short loc_1400868CE
0x140086912  mov     rcx, rbp
0x140086915  call    FveTestRwInvalidRequest
0x14008691a  add     rsp, 60h
0x14008691e  pop     rbp
0x14008691f  retn
0x140086921  mov     esi, 0C0000034h
0x140086926  jmp     loc_140086884
0x14008692b  mov     esi, 0C000000Dh
0x140086930  jmp     loc_140086884
0x140086935  mov     esi, 0C0000001h
0x14008693a  jmp     loc_140086884
```
