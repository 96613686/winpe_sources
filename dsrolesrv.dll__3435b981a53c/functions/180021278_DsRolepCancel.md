# DsRolepCancel

- ea: `0x180021278`
- end: `0x180021395`
- name: `DsRolepCancel`
- size: `285`
- prototype: `__int64 __fastcall(int)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180005860`
- `0x180009ee0`

## callees

- `0x180020dbc`
- `0x180021278`

## import_xrefs

- `ntdll!NtSetEvent` at `0x1800212df`
- `ntdll!NtSetEvent` at `0x1800212df`
- `ntdll!RtlNtStatusToDosError` at `0x1800212eb`
- `ntdll!RtlNtStatusToDosError` at `0x180021367`
- `ntdll!RtlNtStatusToDosError` at `0x1800212eb`
- `ntdll!RtlNtStatusToDosError` at `0x180021367`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800212a3`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800212a3`
- `ntdll!RtlReleaseResource` at `0x18002132e`
- `ntdll!RtlReleaseResource` at `0x18002132e`
- `ntdll!NtWaitForSingleObject` at `0x18002135b`
- `ntdll!NtWaitForSingleObject` at `0x18002135b`
- `NTDSETUP!NtdsInstallCancel` at `0x1800212ca`
- `NTDSETUP!NtdsInstallCancel` at `0x1800212ca`

## string_xrefs

- `0x180021316`: `Cancel already happened or the operation is finished.\n`
- `0x180021340`: `Waiting for the role change operation to complete\n`

## pseudocode

```c
__int64 __fastcall DsRolepCancel(int a1)
{
  int v2; // edi
  ULONG v3; // ebx
  ULONG v4; // eax
  int v5; // eax
  int v6; // eax

  DsRolepLogPrintRoutine(4, "Canceling current operation...\n");
  RtlAcquireResourceExclusive(&DsRolepCurrentOperationHandle, 1u);
  if ( (unsigned int)(dword_18004E1A0 - 3) <= 1 )
  {
    v3 = 0;
    v2 = 0;
    DsRolepLogPrintRoutine(4, "Cancel already happened or the operation is finished.\n");
  }
  else
  {
    v2 = 1;
    if ( (unsigned int)(dword_18004E1A0 - 1) <= 1 )
    {
      v4 = NtdsInstallCancel();
      v3 = v4;
      if ( v4 )
      {
        DsRolepLogPrintRoutine(1, "Unable to cancel the ds%lu\n", v4);
      }
      else
      {
        v5 = NtSetEvent(qword_18004E1C0, 0);
        if ( v5 >= 0 )
          dword_18004E1A0 = 3;
        else
          v3 = RtlNtStatusToDosError(v5);
      }
    }
    else
    {
      v3 = 8222;
    }
  }
  RtlReleaseResource(&DsRolepCurrentOperationHandle);
  if ( !v3 )
  {
    if ( v2 )
    {
      if ( a1 )
      {
        DsRolepLogPrintRoutine(4, "Waiting for the role change operation to complete\n");
        v6 = NtWaitForSingleObject(Handle, 1u, 0);
        if ( v6 < 0 )
          v3 = RtlNtStatusToDosError(v6);
      }
    }
  }
  DsRolepLogPrintRoutine(4, "Request for cancel returning %lu\n", v3);
  return v3;
}

```

## disassembly

```asm
0x180021278  mov     [rsp+arg_0], rbx
0x18002127d  mov     [rsp+arg_8], rsi
0x180021282  push    rdi
0x180021283  sub     rsp, 20h
0x180021287  mov     esi, ecx
0x180021289  lea     rdx, aCancelingCurre; "Canceling current operation...\n"
0x180021290  mov     ecx, 4
0x180021295  call    DsRolepLogPrintRoutine
0x18002129a  mov     dl, 1; Wait
0x18002129c  lea     rcx, DsRolepCurrentOperationHandle; Resource
0x1800212a3  call    cs:__imp_RtlAcquireResourceExclusive
0x1800212a9  mov     edx, cs:dword_18004E1A0
0x1800212af  lea     eax, [rdx-3]
0x1800212b2  cmp     eax, 1
0x1800212b5  jbe     short loc_180021314
0x1800212b7  mov     edi, 1
0x1800212bc  lea     eax, [rdx-1]
0x1800212bf  cmp     eax, edi
0x1800212c1  jbe     short loc_1800212CA
0x1800212c3  mov     ebx, 201Eh
0x1800212c8  jmp     short loc_180021327
0x1800212ca  call    cs:__imp_NtdsInstallCancel
0x1800212d0  mov     ebx, eax
0x1800212d2  test    eax, eax
0x1800212d4  jnz     short loc_180021301
0x1800212d6  mov     rcx, cs:qword_18004E1C0; EventHandle
0x1800212dd  xor     edx, edx; PreviousState
0x1800212df  call    cs:__imp_NtSetEvent
0x1800212e5  test    eax, eax
0x1800212e7  jns     short loc_1800212F5
0x1800212e9  mov     ecx, eax; Status
0x1800212eb  call    cs:__imp_RtlNtStatusToDosError
0x1800212f1  mov     ebx, eax
0x1800212f3  jmp     short loc_180021327
0x1800212f5  mov     cs:dword_18004E1A0, 3
0x1800212ff  jmp     short loc_180021327
0x180021301  mov     r8d, eax
0x180021304  lea     rdx, aUnableToCancel; "Unable to cancel the ds%lu\n"
0x18002130b  mov     ecx, edi
0x18002130d  call    DsRolepLogPrintRoutine
0x180021312  jmp     short loc_180021327
0x180021314  xor     ebx, ebx
0x180021316  lea     rdx, aCancelAlreadyH; "Cancel already happened or the operatio"...
0x18002131d  xor     edi, edi
0x18002131f  lea     ecx, [rbx+4]
0x180021322  call    DsRolepLogPrintRoutine
0x180021327  lea     rcx, DsRolepCurrentOperationHandle; Resource
0x18002132e  call    cs:__imp_RtlReleaseResource
0x180021334  test    ebx, ebx
0x180021336  jnz     short loc_18002136F
0x180021338  test    edi, edi
0x18002133a  jz      short loc_18002136F
0x18002133c  test    esi, esi
0x18002133e  jz      short loc_18002136F
0x180021340  lea     rdx, aWaitingForTheR; "Waiting for the role change operation t"...
0x180021347  lea     ecx, [rbx+4]
0x18002134a  call    DsRolepLogPrintRoutine
0x18002134f  mov     rcx, cs:Handle; Handle
0x180021356  xor     r8d, r8d; Timeout
0x180021359  mov     dl, 1; Alertable
0x18002135b  call    cs:__imp_NtWaitForSingleObject
0x180021361  test    eax, eax
0x180021363  jns     short loc_18002136F
0x180021365  mov     ecx, eax; Status
0x180021367  call    cs:__imp_RtlNtStatusToDosError
0x18002136d  mov     ebx, eax
0x18002136f  mov     r8d, ebx
0x180021372  lea     rdx, aRequestForCanc; "Request for cancel returning %lu\n"
0x180021379  mov     ecx, 4
0x18002137e  call    DsRolepLogPrintRoutine
0x180021383  mov     rsi, [rsp+28h+arg_8]
0x180021388  mov     eax, ebx
0x18002138a  mov     rbx, [rsp+28h+arg_0]
0x18002138f  add     rsp, 20h
0x180021393  pop     rdi
0x180021394  retn
```
