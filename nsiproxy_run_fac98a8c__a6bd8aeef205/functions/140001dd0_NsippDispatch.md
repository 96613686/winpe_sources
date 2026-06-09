# NsippDispatch

- ea: `0x140001dd0`
- end: `0x14000207c`
- name: `NsippDispatch`
- size: `684`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x140001010`
- `0x1400013f0`
- `0x1400015d0`
- `0x140001880`
- `0x140001dd0`
- `0x140002280`
- `0x140002850`
- `0x140002eb0`
- `0x1400032d0`
- `0x1400033c0`
- `0x140003700`
- `0x140003af0`
- `0x140003e20`
- `0x140005c3c`
- `0x1400060e8`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140001f4b`
- `ntoskrnl!ExAllocatePool2` at `0x140001f4b`
- `ntoskrnl!KeInitializeSpinLock` at `0x140001f6e`
- `ntoskrnl!KeInitializeSpinLock` at `0x140001f6e`
- `ntoskrnl!IofCompleteRequest` at `0x140001e74`
- `ntoskrnl!IofCompleteRequest` at `0x140001e74`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001fdd`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001fdd`

## pseudocode

```c
__int64 __fastcall NsippDispatch(__int64 a1, __int64 a2)
{
  char *v2; // rsi
  char v4; // al
  unsigned __int8 v5; // bp
  int v6; // eax
  void *v7; // r12
  __int64 v8; // r14
  unsigned int v9; // r15d
  int AllParameters; // eax
  int IsCallerNsiService; // ebx
  _QWORD *Pool2; // rax
  _QWORD *v14; // rbx

  v2 = *(char **)(a2 + 184);
  v4 = *v2;
  if ( *v2 != 15 )
  {
    switch ( v4 )
    {
      case 0:
        Pool2 = (_QWORD *)ExAllocatePool2(65, 32, 1668305742);
        v14 = Pool2;
        if ( Pool2 )
        {
          Pool2[1] = Pool2;
          *Pool2 = Pool2;
          KeInitializeSpinLock(Pool2 + 3);
          *((_BYTE *)v14 + 16) = 0;
          *(_QWORD *)(*((_QWORD *)v2 + 6) + 24LL) = v14;
          IsCallerNsiService = 0;
        }
        else
        {
          IsCallerNsiService = -1073741670;
        }
        goto LABEL_8;
      case 2:
        ExFreePoolWithTag(*(PVOID *)(*((_QWORD *)v2 + 6) + 24LL), 0);
        IsCallerNsiService = 0;
        goto LABEL_8;
      case 18:
        IsCallerNsiService = NsippCleanup(a1, *(_QWORD *)(a2 + 184));
        goto LABEL_7;
    }
    if ( v4 != 14 )
    {
      IsCallerNsiService = -1073741822;
      goto LABEL_8;
    }
  }
  v5 = *(_BYTE *)(a2 + 64);
  *(_QWORD *)(a2 + 56) = 0;
  v6 = *((_DWORD *)v2 + 6);
  v7 = (void *)*((_QWORD *)v2 + 4);
  v8 = a2 + 56;
  v9 = *((_DWORD *)v2 + 4);
  switch ( v6 )
  {
    case 1179663:
      AllParameters = NsippGetAllParameters(v7);
      break;
    case 1179675:
      AllParameters = NsippEnumerateObjectsAllParameters(v7);
      break;
    case 1179655:
      AllParameters = NsippGetParameter(v7);
      break;
    default:
      switch ( v6 )
      {
        case 1179659:
          AllParameters = NsippSetParameter(v7);
          goto LABEL_6;
        case 1179667:
          AllParameters = NsippSetAllParameters(v7);
          goto LABEL_6;
        case 1179679:
          if ( v5 == 1 )
          {
            IsCallerNsiService = NsippIsCallerNsiService();
            if ( IsCallerNsiService < 0 )
              goto LABEL_7;
          }
          AllParameters = NsippRegisterChangeNotification(v7, v8);
          break;
        case 1179683:
          if ( v5 == 1 )
          {
            IsCallerNsiService = NsippIsCallerNsiService();
            if ( IsCallerNsiService < 0 )
              goto LABEL_7;
          }
          AllParameters = NsippDeregisterChangeNotification(v7);
          break;
        case 1179711:
          AllParameters = NsippRequestChangeNotification(a2, v7, v9, v5);
          goto LABEL_6;
        case 1179712:
          AllParameters = NsippCancelChangeNotification(*(unsigned int **)(a2 + 24), v9);
          goto LABEL_6;
        case 1179719:
          AllParameters = NsippEnumerateObjectsAllPersistentParametersWithMask(v7);
          goto LABEL_6;
        case 1179723:
          AllParameters = NsippGetAllPersistentParametersWithMask(v7);
          goto LABEL_6;
        case 1179727:
          AllParameters = NsippSetAllPersistentParametersWithMask(v7);
          goto LABEL_6;
        default:
          IsCallerNsiService = -1073741822;
          goto LABEL_7;
      }
      break;
  }
LABEL_6:
  IsCallerNsiService = AllParameters;
LABEL_7:
  if ( IsCallerNsiService != 259 )
  {
LABEL_8:
    *(_DWORD *)(a2 + 48) = IsCallerNsiService;
    IofCompleteRequest((PIRP)a2, 2);
  }
  return (unsigned int)IsCallerNsiService;
}

```

## disassembly

```asm
0x140001dd0  push    rbx
0x140001dd2  push    rsi
0x140001dd3  push    rdi
0x140001dd4  sub     rsp, 30h
0x140001dd8  mov     rsi, [rdx+0B8h]
0x140001ddf  mov     rdi, rdx
0x140001de2  movzx   eax, byte ptr [rsi]
0x140001de5  cmp     al, 0Fh
0x140001de7  jnz     loc_140001F33
0x140001ded  mov     [rsp+48h+arg_0], rbp
0x140001df2  xor     ebx, ebx
0x140001df4  movzx   ebp, byte ptr [rdx+40h]
0x140001df8  mov     [rsp+48h+arg_8], r12
0x140001dfd  mov     [rdx+38h], rbx
0x140001e01  mov     eax, [rsi+18h]
0x140001e04  mov     r12, [rsi+20h]
0x140001e08  mov     [rsp+48h+arg_10], r14
0x140001e0d  lea     r14, [rdx+38h]
0x140001e11  mov     [rsp+48h+arg_18], r15
0x140001e16  mov     r15d, [rsi+10h]
0x140001e1a  cmp     eax, 12000Fh
0x140001e1f  jz      short loc_140001E3C
0x140001e21  cmp     eax, 12001Bh
0x140001e26  jnz     short loc_140001E8B
0x140001e28  mov     r9, r14
0x140001e2b  movzx   r8d, bpl
0x140001e2f  mov     edx, r15d
0x140001e32  mov     rcx, r12; Src
0x140001e35  call    NsippEnumerateObjectsAllParameters
0x140001e3a  jmp     short loc_140001E4E
0x140001e3c  mov     r9, r14
0x140001e3f  movzx   r8d, bpl
0x140001e43  mov     edx, r15d
0x140001e46  mov     rcx, r12; Src
0x140001e49  call    NsippGetAllParameters
0x140001e4e  mov     ebx, eax
0x140001e50  mov     r15, [rsp+48h+arg_18]
0x140001e55  mov     r14, [rsp+48h+arg_10]
0x140001e5a  mov     r12, [rsp+48h+arg_8]
0x140001e5f  mov     rbp, [rsp+48h+arg_0]
0x140001e64  cmp     ebx, 103h
0x140001e6a  jz      short loc_140001E80
0x140001e6c  mov     dl, 2; PriorityBoost
0x140001e6e  mov     [rdi+30h], ebx
0x140001e71  mov     rcx, rdi; Irp
0x140001e74  call    cs:__imp_IofCompleteRequest
0x140001e7b  nop     dword ptr [rax+rax+00h]
0x140001e80  mov     eax, ebx
0x140001e82  add     rsp, 30h
0x140001e86  pop     rdi
0x140001e87  pop     rsi
0x140001e88  pop     rbx
0x140001e89  retn
0x140001e8b  cmp     eax, 120007h
0x140001e90  jnz     short loc_140001EA6
0x140001e92  mov     r9, r14
0x140001e95  movzx   r8d, bpl
0x140001e99  mov     edx, r15d
0x140001e9c  mov     rcx, r12; Src
0x140001e9f  call    NsippGetParameter
0x140001ea4  jmp     short loc_140001E4E
0x140001ea6  add     eax, 0FFEDFFF5h; switch 69 cases
0x140001eab  cmp     eax, 44h
0x140001eae  ja      def_140001ED0; jumptable 0000000140001ED0 default case, cases 1179660-1179666,1179668-1179678,1179680-1179682,1179684-1179710,1179713-1179718,1179720-1179722,1179724-1179726
0x140001eb4  lea     rcx, cs:140000000h
0x140001ebb  cdqe
0x140001ebd  movzx   eax, ds:(byte_1400086A0 - 140000000h)[rcx+rax]
0x140001ec5  mov     r10d, ds:(jpt_140001ED0 - 140000000h)[rcx+rax*4]
0x140001ecd  add     r10, rcx
0x140001ed0  jmp     r10; switch jump
0x140001ed6  cmp     bpl, 1; jumptable 0000000140001ED0 case 1179683
0x140001eda  jnz     short loc_140001EEB
0x140001edc  call    NsippIsCallerNsiService
0x140001ee1  mov     ebx, eax
0x140001ee3  test    eax, eax
0x140001ee5  js      loc_140001E50
0x140001eeb  mov     r9, rsi
0x140001eee  movzx   r8d, bpl
0x140001ef2  mov     edx, r15d
0x140001ef5  mov     rcx, r12; Src
0x140001ef8  call    NsippDeregisterChangeNotification
0x140001efd  jmp     loc_140001E4E
0x140001f02  cmp     bpl, 1; jumptable 0000000140001ED0 case 1179679
0x140001f06  jnz     short loc_140001F17
0x140001f08  call    NsippIsCallerNsiService
0x140001f0d  mov     ebx, eax
0x140001f0f  test    eax, eax
0x140001f11  js      loc_140001E50
0x140001f17  mov     r9, rsi
0x140001f1a  mov     [rsp+48h+var_28], r14; __int64
0x140001f1f  movzx   r8d, bpl
0x140001f23  mov     edx, r15d
0x140001f26  mov     rcx, r12; Src
0x140001f29  call    NsippRegisterChangeNotification
0x140001f2e  jmp     loc_140001E4E
0x140001f33  test    al, al
0x140001f35  jnz     loc_140001FCF
0x140001f3b  mov     edx, 20h ; ' '
0x140001f40  mov     ecx, 41h ; 'A'
0x140001f45  mov     r8d, 6370534Eh
0x140001f4b  call    cs:__imp_ExAllocatePool2
0x140001f52  nop     dword ptr [rax+rax+00h]
0x140001f57  mov     rbx, rax
0x140001f5a  test    rax, rax
0x140001f5d  jz      loc_14000203D
0x140001f63  lea     rcx, [rax+18h]; SpinLock
0x140001f67  mov     [rax+8], rax
0x140001f6b  mov     [rax], rax
0x140001f6e  call    cs:__imp_KeInitializeSpinLock
0x140001f75  nop     dword ptr [rax+rax+00h]
0x140001f7a  mov     byte ptr [rbx+10h], 0
0x140001f7e  mov     rcx, [rsi+30h]
0x140001f82  mov     [rcx+18h], rbx
0x140001f86  xor     ebx, ebx
0x140001f88  jmp     loc_140001E6C
0x140001f8d  movzx   r8d, bpl; jumptable 0000000140001ED0 case 1179659
0x140001f91  mov     edx, r15d
0x140001f94  mov     rcx, r12; Src
0x140001f97  call    NsippSetParameter
0x140001f9c  jmp     loc_140001E4E
0x140001fa1  movzx   r9d, bpl; jumptable 0000000140001ED0 case 1179711
0x140001fa5  mov     r8d, r15d
0x140001fa8  mov     rdx, r12
0x140001fab  mov     rcx, rdi
0x140001fae  call    NsippRequestChangeNotification
0x140001fb3  jmp     loc_140001E4E
0x140001fb8  mov     r9, rsi; jumptable 0000000140001ED0 case 1179667
0x140001fbb  movzx   r8d, bpl
0x140001fbf  mov     edx, r15d
0x140001fc2  mov     rcx, r12; Src
0x140001fc5  call    NsippSetAllParameters
0x140001fca  jmp     loc_140001E4E
0x140001fcf  cmp     al, 2
0x140001fd1  jnz     short loc_140002001
0x140001fd3  mov     rcx, [rsi+30h]
0x140001fd7  xor     edx, edx; Tag
0x140001fd9  mov     rcx, [rcx+18h]; P
0x140001fdd  call    cs:__imp_ExFreePoolWithTag
0x140001fe4  nop     dword ptr [rax+rax+00h]
0x140001fe9  xor     ebx, ebx
0x140001feb  jmp     loc_140001E6C
0x140001ff0  mov     rcx, [rdi+18h]; jumptable 0000000140001ED0 case 1179712
0x140001ff4  mov     edx, r15d
0x140001ff7  call    NsippCancelChangeNotification
0x140001ffc  jmp     loc_140001E4E
0x140002001  cmp     al, 12h
0x140002003  jnz     short loc_140002014
0x140002005  mov     rdx, rsi
0x140002008  call    NsippCleanup
0x14000200d  mov     ebx, eax
0x14000200f  jmp     loc_140001E64
0x140002014  cmp     al, 0Eh
0x140002016  jz      loc_140001DED
0x14000201c  mov     ebx, 0C0000002h
0x140002021  jmp     loc_140001E6C
0x140002026  mov     r9, r14; jumptable 0000000140001ED0 case 1179723
0x140002029  movzx   r8d, bpl
0x14000202d  mov     edx, r15d
0x140002030  mov     rcx, r12; Src
0x140002033  call    NsippGetAllPersistentParametersWithMask
0x140002038  jmp     loc_140001E4E
0x14000203d  mov     ebx, 0C000009Ah
0x140002042  jmp     loc_140001E6C
0x140002047  mov     r9, r14; jumptable 0000000140001ED0 case 1179719
0x14000204a  movzx   r8d, bpl
0x14000204e  mov     edx, r15d
0x140002051  mov     rcx, r12; Src
0x140002054  call    NsippEnumerateObjectsAllPersistentParametersWithMask
0x140002059  jmp     loc_140001E4E
0x14000205e  movzx   r8d, bpl; jumptable 0000000140001ED0 case 1179727
0x140002062  mov     edx, r15d
0x140002065  mov     rcx, r12; Src
0x140002068  call    NsippSetAllPersistentParametersWithMask
0x14000206d  jmp     loc_140001E4E
0x140002072  mov     ebx, 0C0000002h; jumptable 0000000140001ED0 default case, cases 1179660-1179666,1179668-1179678,1179680-1179682,1179684-1179710,1179713-1179718,1179720-1179722,1179724-1179726
0x140002077  jmp     loc_140001E50
```
