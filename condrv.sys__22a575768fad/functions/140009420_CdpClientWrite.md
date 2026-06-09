# CdpClientWrite

- ea: `0x140009420`
- end: `0x1400095ab`
- name: `CdpClientWrite`
- size: `395`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140009420`
- `0x14000a5e0`
- `0x14000ac50`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140009510`
- `ntoskrnl!ObfDereferenceObject` at `0x140009553`
- `ntoskrnl!ObfDereferenceObject` at `0x140009510`
- `ntoskrnl!ObfDereferenceObject` at `0x140009553`
- `ntoskrnl!IoGetRequestorProcess` at `0x140009456`
- `ntoskrnl!IoGetRequestorProcess` at `0x140009456`
- `ntoskrnl!IofCompleteRequest` at `0x140009570`
- `ntoskrnl!IofCompleteRequest` at `0x140009570`
- `ntoskrnl!ZwAllocateLocallyUniqueId` at `0x1400094f2`
- `ntoskrnl!ZwAllocateLocallyUniqueId` at `0x1400094f2`

## pseudocode

```c
__int64 __fastcall CdpClientWrite(__int64 a1, __int64 a2)
{
  int v2; // eax
  PVOID v5; // rdi
  PEPROCESS RequestorProcess; // rax
  int ProcessConnection; // ebp
  _QWORD *v8; // rcx
  __int64 v9; // rax
  __int64 v10; // r9
  __int64 v11; // r10
  __int64 v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r8
  _QWORD *v16; // [rsp+40h] [rbp+8h] BYREF
  PVOID Object; // [rsp+50h] [rbp+18h] BYREF

  v2 = *(_DWORD *)(a1 + 32);
  v16 = 0;
  Object = 0;
  v5 = 0;
  if ( (v2 & 1) != 0 )
  {
    v8 = *(_QWORD **)(*(_QWORD *)(a1 + 8) + 224LL);
    if ( !v8 )
    {
      ProcessConnection = -1073741816;
      goto LABEL_18;
    }
    goto LABEL_5;
  }
  RequestorProcess = IoGetRequestorProcess((PIRP)a2);
  if ( !RequestorProcess )
  {
    ProcessConnection = -1073741813;
    goto LABEL_18;
  }
  ProcessConnection = CdGetProcessConnection(&Object, &v16, 0, RequestorProcess);
  if ( ProcessConnection >= 0 )
  {
    v8 = v16;
    v5 = Object;
LABEL_5:
    v9 = *(_QWORD *)(a1 + 8);
    if ( !v9 || v9 == v8[3] )
    {
      v10 = v8[3];
      v11 = v8[5];
      if ( (*(_DWORD *)(a1 + 32) & 2) != 0 )
      {
        v12 = *(_QWORD *)(a1 + 16);
      }
      else if ( *(_DWORD *)(a1 + 16) == 1 )
      {
        v12 = v8[6];
      }
      else
      {
        v12 = v8[7];
      }
      v13 = *(_QWORD *)(a2 + 184);
      v14 = *(_QWORD *)(a2 + 8);
      *(_QWORD *)(v13 - 56) = v12;
      *(_WORD *)(v13 - 72) = 1295;
      *(_QWORD *)(v13 - 64) = v10 + 64;
      *(_QWORD *)(v13 - 48) = v14;
      *(_QWORD *)(v13 - 40) = 0;
      *(_QWORD *)(a2 + 120) = v11;
      ZwAllocateLocallyUniqueId((PLUID)(a2 + 136));
      ProcessConnection = CdAddIoToPipe(a2);
      if ( v5 )
        ObfDereferenceObject(v5);
      if ( ProcessConnection >= 0 )
        return 259;
    }
    else
    {
      if ( (*(_DWORD *)(a1 + 32) & 1) == 0 )
        ObfDereferenceObject(v5);
      ProcessConnection = -1073741816;
    }
  }
LABEL_18:
  *(_DWORD *)(a2 + 48) = ProcessConnection;
  *(_QWORD *)(a2 + 56) = 0;
  IofCompleteRequest((PIRP)a2, 0);
  return (unsigned int)ProcessConnection;
}

```

## disassembly

```asm
0x140009420  mov     [rsp+arg_8], rbx
0x140009425  mov     [rsp+arg_18], rbp
0x14000942a  push    rsi
0x14000942b  push    rdi
0x14000942c  push    r14
0x14000942e  sub     rsp, 20h
0x140009432  mov     eax, [rcx+20h]
0x140009435  xor     r14d, r14d
0x140009438  mov     [rsp+38h+arg_0], r14
0x14000943d  mov     rsi, rdx
0x140009440  mov     [rsp+38h+Object], r14
0x140009445  mov     rbx, rcx
0x140009448  mov     edi, r14d
0x14000944b  test    al, 1
0x14000944d  jnz     loc_140009580
0x140009453  mov     rcx, rdx; Irp
0x140009456  call    cs:__imp_IoGetRequestorProcess
0x14000945d  nop     dword ptr [rax+rax+00h]
0x140009462  test    rax, rax
0x140009465  jz      loc_1400095A4
0x14000946b  mov     r9, rax
0x14000946e  lea     rdx, [rsp+38h+arg_0]
0x140009473  xor     r8d, r8d
0x140009476  lea     rcx, [rsp+38h+Object]
0x14000947b  call    CdGetProcessConnection
0x140009480  mov     ebp, eax
0x140009482  test    eax, eax
0x140009484  js      loc_140009564
0x14000948a  mov     rcx, [rsp+38h+arg_0]
0x14000948f  mov     rdi, [rsp+38h+Object]
0x140009494  mov     rax, [rbx+8]
0x140009498  test    rax, rax
0x14000949b  jnz     loc_14000953F
0x1400094a1  mov     eax, [rbx+20h]
0x1400094a4  mov     r9, [rcx+18h]
0x1400094a8  mov     r10, [rcx+28h]
0x1400094ac  test    al, 2
0x1400094ae  jnz     loc_140009539
0x1400094b4  cmp     dword ptr [rbx+10h], 1
0x1400094b8  jz      loc_14000959B
0x1400094be  mov     rcx, [rcx+38h]
0x1400094c2  mov     rdx, [rsi+0B8h]
0x1400094c9  lea     rax, [r9+40h]
0x1400094cd  mov     r8, [rsi+8]
0x1400094d1  mov     [rdx-38h], rcx
0x1400094d5  lea     rcx, [rsi+88h]; Luid
0x1400094dc  mov     word ptr [rdx-48h], 50Fh
0x1400094e2  mov     [rdx-40h], rax
0x1400094e6  mov     [rdx-30h], r8
0x1400094ea  mov     [rdx-28h], r14
0x1400094ee  mov     [rsi+78h], r10
0x1400094f2  call    cs:__imp_ZwAllocateLocallyUniqueId
0x1400094f9  nop     dword ptr [rax+rax+00h]
0x1400094fe  mov     rcx, rsi
0x140009501  call    CdAddIoToPipe
0x140009506  mov     ebp, eax
0x140009508  test    rdi, rdi
0x14000950b  jz      short loc_14000951C
0x14000950d  mov     rcx, rdi; Object
0x140009510  call    cs:__imp_ObfDereferenceObject
0x140009517  nop     dword ptr [rax+rax+00h]
0x14000951c  test    ebp, ebp
0x14000951e  js      short loc_140009564
0x140009520  mov     eax, 103h
0x140009525  mov     rbx, [rsp+38h+arg_8]
0x14000952a  mov     rbp, [rsp+38h+arg_18]
0x14000952f  add     rsp, 20h
0x140009533  pop     r14
0x140009535  pop     rdi
0x140009536  pop     rsi
0x140009537  retn
0x140009539  mov     rcx, [rbx+10h]
0x14000953d  jmp     short loc_1400094C2
0x14000953f  cmp     rax, [rcx+18h]
0x140009543  jz      loc_1400094A1
0x140009549  mov     eax, [rbx+20h]
0x14000954c  test    al, 1
0x14000954e  jnz     short loc_14000955F
0x140009550  mov     rcx, rdi; Object
0x140009553  call    cs:__imp_ObfDereferenceObject
0x14000955a  nop     dword ptr [rax+rax+00h]
0x14000955f  mov     ebp, 0C0000008h
0x140009564  xor     edx, edx; PriorityBoost
0x140009566  mov     [rsi+30h], ebp
0x140009569  mov     rcx, rsi; Irp
0x14000956c  mov     [rsi+38h], r14
0x140009570  call    cs:__imp_IofCompleteRequest
0x140009577  nop     dword ptr [rax+rax+00h]
0x14000957c  mov     eax, ebp
0x14000957e  jmp     short loc_140009525
0x140009580  mov     rax, [rcx+8]
0x140009584  mov     rcx, [rax+0E0h]
0x14000958b  test    rcx, rcx
0x14000958e  jnz     loc_140009494
0x140009594  mov     ebp, 0C0000008h
0x140009599  jmp     short loc_140009564
0x14000959b  mov     rcx, [rcx+30h]
0x14000959f  jmp     loc_1400094C2
0x1400095a4  mov     ebp, 0C000000Bh
0x1400095a9  jmp     short loc_140009564
```
