# FIPostMoveFile

- ea: `0x140001644`
- end: `0x14000177d`
- name: `FIPostMoveFile`
- size: `313`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x140001480`

## callees

- `0x140001644`
- `0x140003920`

## import_xrefs

- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400016df`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400016df`
- `ntoskrnl!PfFileInfoNotify` at `0x14000171f`
- `ntoskrnl!PfFileInfoNotify` at `0x14000171f`
- `ntoskrnl!IoFileObjectType` at `0x1400016bd`
- `ntoskrnl!ObfDereferenceObject` at `0x140001736`
- `ntoskrnl!ObfDereferenceObject` at `0x140001736`
- `FLTMGR!FltIs32bitProcess` at `0x140001692`
- `FLTMGR!FltIs32bitProcess` at `0x140001692`

## pseudocode

```c
__int64 __fastcall FIPostMoveFile(struct _FLT_CALLBACK_DATA *a1)
{
  BOOLEAN v2; // al
  PFLT_IO_PARAMETER_BLOCK Iopb; // rcx
  unsigned int Options; // edx
  PMDL v5; // rcx
  NTSTATUS v6; // ebx
  PVOID Object; // [rsp+30h] [rbp-40h] BYREF
  __int128 v9; // [rsp+38h] [rbp-38h] BYREF
  __int128 *v10; // [rsp+48h] [rbp-28h]
  __int128 v11; // [rsp+50h] [rbp-20h] BYREF

  v10 = 0;
  v9 = 0;
  Object = 0;
  if ( a1->IoStatus.Status < 0 )
    return (unsigned int)-1073741823;
  v11 = (unsigned __int64)_InterlockedExchangeAdd64((_QWORD *)&xmmword_1400093B0 + 1, 1u);
  v2 = FltIs32bitProcess(a1);
  Iopb = a1->Iopb;
  Options = Iopb->Parameters.Create.Options;
  if ( v2 )
  {
    if ( Options >= 0x20 )
    {
      v5 = (PMDL)*(unsigned int *)Iopb->Parameters.CreatePipe.Parameters;
LABEL_5:
      v6 = ObReferenceObjectByHandle(v5, 0, (POBJECT_TYPE)IoFileObjectType, a1->RequestorMode, &Object, 0);
      if ( v6 >= 0 )
      {
        *((_QWORD *)&v11 + 1) = *((_QWORD *)Object + 3);
        *((_QWORD *)&v9 + 1) = 1;
        *(_QWORD *)&v9 = 0xD0000000FLL;
        v10 = &v11;
        v6 = PfFileInfoNotify(&v9);
      }
      goto LABEL_7;
    }
  }
  else if ( Options >= 0x20 )
  {
    v5 = *Iopb->Parameters.MdlRead.MdlChain;
    goto LABEL_5;
  }
  v6 = -1073741306;
LABEL_7:
  if ( Object )
    ObfDereferenceObject(Object);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140001644  mov     [rsp-8+arg_8], rbx
0x140001649  push    rbp
0x14000164a  mov     rbp, rsp
0x14000164d  sub     rsp, 70h
0x140001651  mov     rax, cs:__security_cookie
0x140001658  xor     rax, rsp
0x14000165b  mov     [rbp+var_10], rax
0x14000165f  xor     eax, eax
0x140001661  xorps   xmm0, xmm0
0x140001664  mov     rbx, rcx
0x140001667  mov     [rbp+var_28], rax
0x14000166b  movups  [rbp+var_38], xmm0
0x14000166f  mov     [rbp+var_40], rax
0x140001673  cmp     [rcx+18h], eax
0x140001676  jl      loc_14000176B
0x14000167c  movups  [rbp+var_20], xmm0
0x140001680  mov     eax, 1
0x140001685  lock xadd qword ptr cs:xmmword_1400093B0+8, rax
0x14000168e  mov     qword ptr [rbp+var_20], rax
0x140001692  call    cs:__imp_FltIs32bitProcess
0x140001699  nop     dword ptr [rax+rax+00h]
0x14000169e  mov     rcx, [rbx+10h]
0x1400016a2  mov     edx, [rcx+20h]
0x1400016a5  test    al, al
0x1400016a7  jnz     loc_14000175F
0x1400016ad  cmp     edx, 20h ; ' '
0x1400016b0  jb      loc_140001764
0x1400016b6  mov     rax, [rcx+30h]
0x1400016ba  mov     rcx, [rax]; Handle
0x1400016bd  mov     r8, cs:__imp_IoFileObjectType
0x1400016c4  lea     rax, [rbp+var_40]
0x1400016c8  mov     r9b, [rbx+50h]; AccessMode
0x1400016cc  xor     edx, edx; DesiredAccess
0x1400016ce  mov     [rsp+70h+HandleInformation], 0; HandleInformation
0x1400016d7  mov     [rsp+70h+Object], rax; Object
0x1400016dc  mov     r8, [r8]; ObjectType
0x1400016df  call    cs:__imp_ObReferenceObjectByHandle
0x1400016e6  nop     dword ptr [rax+rax+00h]
0x1400016eb  mov     ebx, eax
0x1400016ed  test    eax, eax
0x1400016ef  js      short loc_14000172D
0x1400016f1  mov     rax, [rbp+var_40]
0x1400016f5  mov     rcx, [rax+18h]
0x1400016f9  lea     rax, [rbp+var_20]
0x1400016fd  mov     qword ptr [rbp+var_20+8], rcx
0x140001701  lea     rcx, [rbp+var_38]
0x140001705  mov     qword ptr [rbp+var_38+8], 1
0x14000170d  mov     dword ptr [rbp+var_38], 0Fh
0x140001714  mov     dword ptr [rbp+var_38+4], 0Dh
0x14000171b  mov     [rbp+var_28], rax
0x14000171f  call    cs:__imp_PfFileInfoNotify
0x140001726  nop     dword ptr [rax+rax+00h]
0x14000172b  mov     ebx, eax
0x14000172d  mov     rcx, [rbp+var_40]; Object
0x140001731  test    rcx, rcx
0x140001734  jz      short loc_140001742
0x140001736  call    cs:__imp_ObfDereferenceObject
0x14000173d  nop     dword ptr [rax+rax+00h]
0x140001742  mov     eax, ebx
0x140001744  mov     rcx, [rbp+var_10]
0x140001748  xor     rcx, rsp; StackCookie
0x14000174b  call    __security_check_cookie
0x140001750  mov     rbx, [rsp+70h+arg_8]
0x140001758  add     rsp, 70h
0x14000175c  pop     rbp
0x14000175d  retn
0x14000175f  cmp     edx, 20h ; ' '
0x140001762  jnb     short loc_140001772
0x140001764  mov     ebx, 0C0000206h
0x140001769  jmp     short loc_14000172D
0x14000176b  mov     ebx, 0C0000001h
0x140001770  jmp     short loc_140001742
0x140001772  mov     rax, [rcx+30h]
0x140001776  mov     ecx, [rax]
0x140001778  jmp     loc_1400016BD
```
