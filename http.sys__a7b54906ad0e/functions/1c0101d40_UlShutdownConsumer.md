# UlShutdownConsumer

- ea: `0x1c0101d40`
- end: `0x1c0101e7e`
- name: `UlShutdownConsumer`
- size: `318`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1c011d470`

## callees

- `0x1c0003240`
- `0x1c008f21c`
- `0x1c008f680`
- `0x1c0101d40`
- `0x1c0103720`

## import_xrefs

- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1c0101dcd`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1c0101dcd`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1c0101daa`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1c0101daa`
- `ntoskrnl!IofCompleteRequest` at `0x1c0101e3d`
- `ntoskrnl!IofCompleteRequest` at `0x1c0101e3d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c0101dd9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c0101dd9`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c0101d97`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c0101d97`

## pseudocode

```c
__int64 __fastcall UlShutdownConsumer(__int64 a1)
{
  __int64 v1; // rdi
  _QWORD *v3; // rcx
  __int64 v4; // rax
  IRP *v5; // rcx
  __int64 result; // rax
  _QWORD v7[2]; // [rsp+20h] [rbp-20h] BYREF
  _QWORD v8[2]; // [rsp+30h] [rbp-10h] BYREF

  v1 = *(_QWORD *)(a1 + 8);
  if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
    WPP_SF_q(120, WPP_80d4b18777633ecb8759c7c8a3c5c10e_Traceguids, a1);
  v8[1] = v8;
  v8[0] = v8;
  v7[1] = v7;
  v7[0] = v7;
  KeEnterCriticalRegion();
  ExAcquireCacheAwarePushLockExclusive(*(_QWORD *)(v1 + 280));
  UlpFlushPendingConsumerIo(a1, v7, v8);
  ExReleaseCacheAwarePushLockExclusive(*(_QWORD *)(v1 + 280));
  KeLeaveCriticalRegion();
  UlpRedeliverFlushedRequests(v1);
  while ( 1 )
  {
    v3 = (_QWORD *)v7[0];
    if ( (_QWORD *)v7[0] == v7 )
      break;
    if ( *(_QWORD **)(v7[0] + 8LL) != v7 || (v4 = *(_QWORD *)v7[0], *(_QWORD *)(*(_QWORD *)v7[0] + 8LL) != v7[0]) )
      __fastfail(3u);
    v7[0] = *(_QWORD *)v7[0];
    *(_QWORD *)(v4 + 8) = v7;
    *v3 = 0;
    v3[1] = 0;
    v5 = (IRP *)(v3 - 21);
    v5->IoStatus.Status = -1073741536;
    v5->IoStatus.Information = 0;
    IofCompleteRequest(v5, 0);
  }
  result = LODWORD(WPP_MAIN_CB.Queue.ListEntry.Flink);
  if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
    return WPP_SF_(121, WPP_80d4b18777633ecb8759c7c8a3c5c10e_Traceguids);
  return result;
}

```

## disassembly

```asm
0x1c0101d40  mov     [rsp-8+arg_0], rbx
0x1c0101d45  mov     [rsp-8+arg_8], rdi
0x1c0101d4a  push    rbp
0x1c0101d4b  mov     rbp, rsp
0x1c0101d4e  sub     rsp, 40h
0x1c0101d52  mov     rdi, [rcx+8]
0x1c0101d56  mov     rbx, rcx
0x1c0101d59  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c0101d5f  test    al, al
0x1c0101d61  jns     short loc_1C0101D77
0x1c0101d63  mov     ecx, 78h ; 'x'
0x1c0101d68  lea     rdx, WPP_80d4b18777633ecb8759c7c8a3c5c10e_Traceguids
0x1c0101d6f  mov     r8, rbx
0x1c0101d72  call    WPP_SF_q
0x1c0101d77  lea     rax, [rbp+var_10]
0x1c0101d7b  mov     [rbp+var_8], rax
0x1c0101d7f  lea     rax, [rbp+var_10]
0x1c0101d83  mov     [rbp+var_10], rax
0x1c0101d87  lea     rax, [rbp+var_20]
0x1c0101d8b  mov     [rbp+var_18], rax
0x1c0101d8f  lea     rax, [rbp+var_20]
0x1c0101d93  mov     [rbp+var_20], rax
0x1c0101d97  call    cs:__imp_KeEnterCriticalRegion
0x1c0101d9e  nop     dword ptr [rax+rax+00h]
0x1c0101da3  mov     rcx, [rdi+118h]
0x1c0101daa  call    cs:__imp_ExAcquireCacheAwarePushLockExclusive
0x1c0101db1  nop     dword ptr [rax+rax+00h]
0x1c0101db6  lea     r8, [rbp+var_10]
0x1c0101dba  mov     rcx, rbx
0x1c0101dbd  lea     rdx, [rbp+var_20]
0x1c0101dc1  call    UlpFlushPendingConsumerIo
0x1c0101dc6  mov     rcx, [rdi+118h]
0x1c0101dcd  call    cs:__imp_ExReleaseCacheAwarePushLockExclusive
0x1c0101dd4  nop     dword ptr [rax+rax+00h]
0x1c0101dd9  call    cs:__imp_KeLeaveCriticalRegion
0x1c0101de0  nop     dword ptr [rax+rax+00h]
0x1c0101de5  mov     r8, rbx
0x1c0101de8  lea     rdx, [rbp+var_10]
0x1c0101dec  mov     rcx, rdi; int
0x1c0101def  call    UlpRedeliverFlushedRequests
0x1c0101df4  xor     ebx, ebx
0x1c0101df6  mov     rcx, [rbp+var_20]
0x1c0101dfa  lea     rax, [rbp+var_20]
0x1c0101dfe  cmp     rcx, rax
0x1c0101e01  jz      short loc_1C0101E52
0x1c0101e03  lea     rax, [rbp+var_20]
0x1c0101e07  cmp     [rcx+8], rax
0x1c0101e0b  jnz     short loc_1C0101E4B
0x1c0101e0d  mov     rax, [rcx]
0x1c0101e10  cmp     [rax+8], rcx
0x1c0101e14  jnz     short loc_1C0101E4B
0x1c0101e16  mov     [rbp+var_20], rax
0x1c0101e1a  lea     rdx, [rbp+var_20]
0x1c0101e1e  mov     [rax+8], rdx
0x1c0101e22  xor     edx, edx; PriorityBoost
0x1c0101e24  mov     [rcx], rbx
0x1c0101e27  mov     [rcx+8], rbx
0x1c0101e2b  add     rcx, 0FFFFFFFFFFFFFF58h; Irp
0x1c0101e32  mov     dword ptr [rcx+30h], 0C0000120h
0x1c0101e39  mov     [rcx+38h], rbx
0x1c0101e3d  call    cs:__imp_IofCompleteRequest
0x1c0101e44  nop     dword ptr [rax+rax+00h]
0x1c0101e49  jmp     short loc_1C0101DF6
0x1c0101e4b  mov     ecx, 3
0x1c0101e50  int     29h; Win8: RtlFailFast(ecx)
0x1c0101e52  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c0101e58  test    al, al
0x1c0101e5a  jns     short loc_1C0101E6D
0x1c0101e5c  mov     ecx, 79h ; 'y'
0x1c0101e61  lea     rdx, WPP_80d4b18777633ecb8759c7c8a3c5c10e_Traceguids
0x1c0101e68  call    WPP_SF_
0x1c0101e6d  mov     rbx, [rsp+40h+arg_0]
0x1c0101e72  mov     rdi, [rsp+40h+arg_8]
0x1c0101e77  add     rsp, 40h
0x1c0101e7b  pop     rbp
0x1c0101e7c  retn
```
