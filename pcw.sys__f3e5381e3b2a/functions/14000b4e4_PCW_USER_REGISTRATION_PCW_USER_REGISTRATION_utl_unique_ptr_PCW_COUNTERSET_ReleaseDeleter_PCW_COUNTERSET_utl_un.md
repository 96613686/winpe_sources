# PCW_USER_REGISTRATION::PCW_USER_REGISTRATION(utl::unique_ptr<PCW_COUNTERSET,ReleaseDeleter<PCW_COUNTERSET>> &&,utl::unique_ptr<void,GenericDeleter<void,__int64 (void *),&ObfDereferenceObject(void *)>>,void * const,utl::unique_ptr<_IO_MINI_COMPLETION_PACKET_USER,GenericDeleter<_IO_MINI_COMPLETION_PACKET_USER,void (_IO_MINI_COMPLETION_PACKET_USER *),&IoFreeMiniCompletionPacket(_IO_MINI_COMPLETION_PACKET_USER *)>> &&)

- ea: `0x14000b4e4`
- end: `0x14000b5aa`
- name: `??0PCW_USER_REGISTRATION@@AEAA@$$QEAV?$unique_ptr@VPCW_COUNTERSET@@U?$ReleaseDeleter@VPCW_COUNTERSET@@@@@utl@@V?$unique_ptr@XU?$GenericDeleter@X$$A6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@Z@@@2@QEAX$$QEAV?$unique_ptr@U_IO_MINI_COMPLETION_PACKET_USER@@U?$GenericDeleter@U_IO_MINI_COMPLETION_PACKET_USER@@$$A6AXPEAU1@@Z$1?IoFreeMiniCompletionPacket@@YAX0@Z@@@2@@Z`
- size: `198`
- prototype: `char *__fastcall(char *Object, __int64 *, PVOID *, __int64, __int64 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000bc80`

## callees

- `0x14000b4e4`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14000b58a`
- `ntoskrnl!ObfDereferenceObject` at `0x14000b58a`
- `ntoskrnl!ObfReferenceObject` at `0x14000b576`
- `ntoskrnl!ObfReferenceObject` at `0x14000b576`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14000b54e`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14000b54e`

## pseudocode

```c
char *__fastcall PCW_USER_REGISTRATION::PCW_USER_REGISTRATION(
        char *Object,
        __int64 *a2,
        PVOID *a3,
        __int64 a4,
        __int64 *a5)
{
  __int64 v7; // rax
  char *v8; // rbx
  PVOID v9; // rax
  __int64 v10; // rcx
  unsigned int CurrentProcessId; // eax
  __int64 v12; // rax

  *(_DWORD *)Object = 1;
  *(_OWORD *)(Object + 8) = 0;
  v7 = *a2;
  *a2 = 0;
  v8 = Object + 64;
  *((_QWORD *)Object + 3) = v7;
  *((_QWORD *)Object + 4) = 0;
  v9 = *a3;
  *a3 = 0;
  *((_QWORD *)Object + 5) = v9;
  *((_QWORD *)Object + 6) = a4;
  v10 = *a5;
  *a5 = 0;
  *((_QWORD *)Object + 7) = v10;
  *(_OWORD *)v8 = 0;
  *((_QWORD *)Object + 10) = 0;
  CurrentProcessId = (unsigned int)PsGetCurrentProcessId();
  *((_DWORD *)Object + 23) = 0;
  *((_DWORD *)Object + 22) = CurrentProcessId;
  v12 = *((_QWORD *)Object + 7);
  *((_QWORD *)v8 + 1) = v8;
  *(_QWORD *)v8 = v8;
  *(_QWORD *)(v12 + 64) = Object;
  ObfReferenceObject(Object);
  if ( *a3 )
    ObfDereferenceObject(*a3);
  return Object;
}

```

## disassembly

```asm
0x14000b4e4  mov     [rsp+arg_0], rbx
0x14000b4e9  mov     [rsp+arg_8], rsi
0x14000b4ee  push    rdi
0x14000b4ef  sub     rsp, 20h
0x14000b4f3  mov     dword ptr [rcx], 1
0x14000b4f9  mov     rsi, rcx
0x14000b4fc  xorps   xmm0, xmm0
0x14000b4ff  mov     rdi, r8
0x14000b502  movups  xmmword ptr [rcx+8], xmm0
0x14000b506  mov     rax, [rdx]
0x14000b509  mov     qword ptr [rdx], 0
0x14000b510  lea     rbx, [rsi+40h]
0x14000b514  mov     [rcx+18h], rax
0x14000b518  xor     eax, eax
0x14000b51a  mov     [rcx+20h], rax
0x14000b51e  mov     rax, [r8]
0x14000b521  mov     qword ptr [r8], 0
0x14000b528  mov     [rcx+28h], rax
0x14000b52c  mov     rax, [rsp+28h+arg_20]
0x14000b531  mov     [rcx+30h], r9
0x14000b535  mov     rcx, [rax]
0x14000b538  mov     qword ptr [rax], 0
0x14000b53f  mov     [rsi+38h], rcx
0x14000b543  movups  xmmword ptr [rbx], xmm0
0x14000b546  mov     qword ptr [rsi+50h], 0
0x14000b54e  call    cs:__imp_PsGetCurrentProcessId
0x14000b555  nop     dword ptr [rax+rax+00h]
0x14000b55a  mov     dword ptr [rsi+5Ch], 0
0x14000b561  mov     rcx, rsi; Object
0x14000b564  mov     [rsi+58h], eax
0x14000b567  mov     rax, [rsi+38h]
0x14000b56b  mov     [rbx+8], rbx
0x14000b56f  mov     [rbx], rbx
0x14000b572  mov     [rax+40h], rsi
0x14000b576  call    cs:__imp_ObfReferenceObject
0x14000b57d  nop     dword ptr [rax+rax+00h]
0x14000b582  mov     rcx, [rdi]; Object
0x14000b585  test    rcx, rcx
0x14000b588  jz      short loc_14000B596
0x14000b58a  call    cs:__imp_ObfDereferenceObject
0x14000b591  nop     dword ptr [rax+rax+00h]
0x14000b596  mov     rbx, [rsp+28h+arg_0]
0x14000b59b  mov     rax, rsi
0x14000b59e  mov     rsi, [rsp+28h+arg_8]
0x14000b5a3  add     rsp, 20h
0x14000b5a7  pop     rdi
0x14000b5a8  retn
```
