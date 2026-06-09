# EtwpStopLogger(_WMI_LOGGER_INFORMATION *,ulong,_EVENT_FILTER_DESCRIPTOR *)

- ea: `0x1800138d0`
- end: `0x180013bc2`
- name: `?EtwpStopLogger@@YAKPEAU_WMI_LOGGER_INFORMATION@@KPEAU_EVENT_FILTER_DESCRIPTOR@@@Z`
- size: `754`
- prototype: `unsigned int __fastcall(struct _WMI_LOGGER_INFORMATION *, unsigned int, struct _EVENT_FILTER_DESCRIPTOR *)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task, installer_update`

## callers

- `0x1800099c0`
- `0x18000a300`

## callees

- `0x180001560`
- `0x180001e82`
- `0x180001eca`
- `0x180001ee2`
- `0x180001ef0`
- `0x180013504`
- `0x18001356c`
- `0x1800138d0`
- `0x180014468`
- `0x1800144a4`

## import_xrefs

- `ntdll!RtlGetCurrentServiceSessionId` at `0x18001395d`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x18001398b`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x1800139ba`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x180013a6b`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x180013aaa`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x180013ae5`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x18001395d`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x18001398b`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x1800139ba`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x180013a6b`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x180013aaa`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x180013ae5`
- `ext-ms-win-eventing-rundown-l1-1-0!EtwLogSysConfigRundown` at `0x180013b55`
- `ext-ms-win-eventing-rundown-l1-1-0!EtwLogSysConfigRundown` at `0x180013b55`

## pseudocode

```c
NTSTATUS __fastcall EtwpStopLogger(
        struct _WMI_LOGGER_INFORMATION *a1,
        unsigned int a2,
        struct _EVENT_FILTER_DESCRIPTOR *a3)
{
  bool v4; // zf
  int Logger; // edi
  char v6; // r15
  __int64 v7; // rbp
  __int64 v8; // rcx
  char v9; // r12
  __int64 v10; // r14
  __int64 v11; // rcx
  char v12; // r13
  __int64 v13; // rsi
  const wchar_t *v14; // rcx
  char v15; // al
  unsigned int v16; // edi
  unsigned __int64 v17; // rcx
  NTSTATUS result; // eax
  char v19; // [rsp+30h] [rbp-68h]
  int v20; // [rsp+34h] [rbp-64h] BYREF
  __int128 v21; // [rsp+38h] [rbp-60h] BYREF
  __int128 v22; // [rsp+48h] [rbp-50h]

  v4 = (*((_DWORD *)a1 + 16) & 0x800) == 0;
  v20 = 0;
  if ( !v4 || (*((_BYTE *)a1 + 11) & 1) != 0 )
    return EtwpSendUmLogRequest(2, a1, a2, a3);
  Logger = EtwpQueryLogger(a1, a2, a3);
  if ( *(_OWORD *)((char *)a1 + 24) == *(_OWORD *)&SystemTraceControlGuid
    || *(_OWORD *)((char *)a1 + 24) == CKCLGuid
    || (v6 = 0, (*((_DWORD *)a1 + 16) & 0x2000000) != 0) )
  {
    v6 = 1;
  }
  v7 = 2147353480;
  if ( (unsigned int)((__int64 (*)(void))RtlGetCurrentServiceSessionId)() )
    v8 = (__int64)NtCurrentPeb()->HotpatchInformation + 558;
  else
    v8 = 2147353480;
  v9 = *(_BYTE *)v8;
  v10 = 2147353472;
  if ( (unsigned int)((__int64 (*)(void))RtlGetCurrentServiceSessionId)() )
    v11 = (__int64)NtCurrentPeb()->HotpatchInformation + 550;
  else
    v11 = 2147353472;
  v12 = *(_BYTE *)v11;
  v13 = 2147353482;
  if ( (unsigned int)((__int64 (*)(void))RtlGetCurrentServiceSessionId)() )
    v14 = (const wchar_t *)((char *)NtCurrentPeb()->HotpatchInformation + 560);
  else
    v14 = (const wchar_t *)2147353482;
  v15 = *(_BYTE *)v14;
  v19 = *(_BYTE *)v14;
  if ( v6 )
    goto LABEL_26;
  if ( *((_WORD *)a1 + 72) )
  {
    v14 = (const wchar_t *)*((_QWORD *)a1 + 19);
    if ( v14 )
    {
      if ( !wcsicmp(v14, L"Circular Kernel Context Logger")
        || !wcsicmp(*((const wchar_t **)a1 + 19), L"NT Kernel Logger") )
      {
        v6 = 1;
        goto LABEL_26;
      }
      v15 = v19;
    }
  }
  if ( v12 || v9 || v15 )
  {
LABEL_26:
    if ( Logger >= 0 && (*((_DWORD *)a1 + 16) & 0x400) == 0 )
    {
      v16 = *((unsigned __int16 *)a1 + 4);
      if ( v9 )
      {
        if ( (unsigned int)RtlGetCurrentServiceSessionId(v14, 0) )
          v7 = (__int64)NtCurrentPeb()->HotpatchInformation + 558;
        if ( (_WORD)v16 == *(unsigned __int8 *)v7 )
          EtwpHeapRundown(v16, 2);
      }
      if ( v12 )
      {
        if ( (unsigned int)RtlGetCurrentServiceSessionId(v14, 0) )
          v10 = (__int64)NtCurrentPeb()->HotpatchInformation + 550;
        if ( (_WORD)v16 == *(unsigned __int8 *)v10 )
          EtwpHeapRundown(v16, 0);
      }
      if ( v19 )
      {
        if ( (unsigned int)RtlGetCurrentServiceSessionId(v14, 0) )
          v13 = (__int64)NtCurrentPeb()->HotpatchInformation + 560;
        if ( (_WORD)v16 == *(unsigned __int8 *)v13 )
          EtwpHeapRundown(v16, 1);
      }
      if ( v6 )
      {
        v17 = *((_QWORD *)a1 + 1);
        v21 = 0;
        v22 = 0;
        EtwpQueryGroupMaskForRundown(v17, (struct _PERFINFO_GROUPMASK *)&v21);
        if ( (unsigned __int8)IsEtwLogHeapRundownPresent() )
        {
          if ( (DWORD2(v22) & 0x1FFFFFFF) != 0 )
            EtwLogSysConfigRundown((unsigned __int16)v16, &v21);
        }
      }
    }
  }
  result = NtTraceControl_0(2, a1, *(unsigned int *)a1, a1, *(_DWORD *)a1, &v20);
  if ( result )
    return RtlNtStatusToDosError_0(result);
  return result;
}

```

## disassembly

```asm
0x1800138d0  mov     [rsp+arg_18], rbx
0x1800138d5  push    rbp
0x1800138d6  push    rsi
0x1800138d7  push    rdi
0x1800138d8  push    r12
0x1800138da  push    r13
0x1800138dc  push    r14
0x1800138de  push    r15
0x1800138e0  sub     rsp, 60h
0x1800138e4  mov     rax, cs:__security_cookie
0x1800138eb  xor     rax, rsp
0x1800138ee  mov     [rsp+98h+var_40], rax
0x1800138f3  xor     esi, esi
0x1800138f5  mov     rbx, rcx
0x1800138f8  test    dword ptr [rcx+40h], 800h
0x1800138ff  mov     [rsp+98h+var_64], esi
0x180013903  jnz     loc_180013B8A
0x180013909  test    byte ptr [rcx+0Bh], 1
0x18001390d  jnz     loc_180013B8A
0x180013913  call    ?EtwpQueryLogger@@YAKPEAU_WMI_LOGGER_INFORMATION@@KPEAU_EVENT_FILTER_DESCRIPTOR@@@Z; EtwpQueryLogger(_WMI_LOGGER_INFORMATION *,ulong,_EVENT_FILTER_DESCRIPTOR *)
0x180013918  mov     rcx, [rbx+18h]
0x18001391c  mov     edi, eax
0x18001391e  cmp     rcx, qword ptr cs:SystemTraceControlGuid.Data1
0x180013925  jnz     short loc_180013934
0x180013927  mov     rcx, [rbx+20h]
0x18001392b  cmp     rcx, qword ptr cs:SystemTraceControlGuid.Data4
0x180013932  jz      short loc_18001395A
0x180013934  mov     rax, [rbx+18h]
0x180013938  cmp     rax, qword ptr cs:CKCLGuid
0x18001393f  jnz     short loc_18001394E
0x180013941  mov     rax, [rbx+20h]
0x180013945  cmp     rax, qword ptr cs:CKCLGuid+8
0x18001394c  jz      short loc_18001395A
0x18001394e  test    dword ptr [rbx+40h], 2000000h
0x180013955  mov     r15b, sil
0x180013958  jz      short loc_18001395D
0x18001395a  mov     r15b, 1
0x18001395d  call    cs:__imp_RtlGetCurrentServiceSessionId
0x180013963  mov     ebp, 7FFE0388h
0x180013968  test    eax, eax
0x18001396a  jz      short loc_180013985
0x18001396c  mov     rax, gs:60h
0x180013975  mov     rcx, [rax+90h]
0x18001397c  add     rcx, 22Eh
0x180013983  jmp     short loc_180013988
0x180013985  mov     rcx, rbp
0x180013988  mov     r12b, [rcx]
0x18001398b  call    cs:__imp_RtlGetCurrentServiceSessionId
0x180013991  mov     r14d, 7FFE0380h
0x180013997  test    eax, eax
0x180013999  jz      short loc_1800139B4
0x18001399b  mov     rax, gs:60h
0x1800139a4  mov     rcx, [rax+90h]
0x1800139ab  add     rcx, 226h
0x1800139b2  jmp     short loc_1800139B7
0x1800139b4  mov     rcx, r14
0x1800139b7  mov     r13b, [rcx]
0x1800139ba  call    cs:__imp_RtlGetCurrentServiceSessionId
0x1800139c0  xor     edx, edx
0x1800139c2  mov     esi, 7FFE038Ah
0x1800139c7  test    eax, eax
0x1800139c9  jz      short loc_1800139E4
0x1800139cb  mov     rax, gs:60h
0x1800139d4  mov     rcx, [rax+90h]
0x1800139db  add     rcx, 230h
0x1800139e2  jmp     short loc_1800139E7
0x1800139e4  mov     rcx, rsi
0x1800139e7  mov     al, [rcx]
0x1800139e9  mov     [rsp+98h+var_68], al
0x1800139ed  test    r15b, r15b
0x1800139f0  jnz     short loc_180013A4D
0x1800139f2  cmp     [rbx+90h], dx
0x1800139f9  jbe     short loc_180013A3B
0x1800139fb  mov     rcx, [rbx+98h]; String1
0x180013a02  test    rcx, rcx
0x180013a05  jz      short loc_180013A3B
0x180013a07  lea     rdx, aCircularKernel_0; "Circular Kernel Context Logger"
0x180013a0e  call    _wcsicmp
0x180013a13  xor     edx, edx
0x180013a15  test    eax, eax
0x180013a17  jz      short loc_180013A32
0x180013a19  mov     rcx, [rbx+98h]; String1
0x180013a20  lea     rdx, aNtKernelLogger_0; "NT Kernel Logger"
0x180013a27  call    _wcsicmp
0x180013a2c  xor     edx, edx
0x180013a2e  test    eax, eax
0x180013a30  jnz     short loc_180013A37
0x180013a32  mov     r15b, 1
0x180013a35  jmp     short loc_180013A4D
0x180013a37  mov     al, [rsp+98h+var_68]
0x180013a3b  test    r13b, r13b
0x180013a3e  jnz     short loc_180013A4D
0x180013a40  test    r12b, r12b
0x180013a43  jnz     short loc_180013A4D
0x180013a45  test    al, al
0x180013a47  jz      loc_180013B5B
0x180013a4d  test    edi, edi
0x180013a4f  js      loc_180013B5B
0x180013a55  test    dword ptr [rbx+40h], 400h
0x180013a5c  jnz     loc_180013B5B
0x180013a62  movzx   edi, word ptr [rbx+8]
0x180013a66  test    r12b, r12b
0x180013a69  jz      short loc_180013AA5
0x180013a6b  call    cs:__imp_RtlGetCurrentServiceSessionId
0x180013a71  xor     edx, edx
0x180013a73  test    eax, eax
0x180013a75  jz      short loc_180013A8E
0x180013a77  mov     rax, gs:60h
0x180013a80  mov     rbp, [rax+90h]
0x180013a87  add     rbp, 22Eh
0x180013a8e  movzx   eax, byte ptr [rbp+0]
0x180013a92  cmp     di, ax
0x180013a95  jnz     short loc_180013AA5
0x180013a97  mov     ecx, edi
0x180013a99  mov     edx, 2
0x180013a9e  call    ?EtwpHeapRundown@@YAJKW4_HEAP_RUNDOWN_CLASS@@@Z; EtwpHeapRundown(ulong,_HEAP_RUNDOWN_CLASS)
0x180013aa3  xor     edx, edx
0x180013aa5  test    r13b, r13b
0x180013aa8  jz      short loc_180013ADF
0x180013aaa  call    cs:__imp_RtlGetCurrentServiceSessionId
0x180013ab0  xor     edx, edx
0x180013ab2  test    eax, eax
0x180013ab4  jz      short loc_180013ACD
0x180013ab6  mov     rax, gs:60h
0x180013abf  mov     r14, [rax+90h]
0x180013ac6  add     r14, 226h
0x180013acd  movzx   eax, byte ptr [r14]
0x180013ad1  cmp     di, ax
0x180013ad4  jnz     short loc_180013ADF
0x180013ad6  mov     ecx, edi
0x180013ad8  call    ?EtwpHeapRundown@@YAJKW4_HEAP_RUNDOWN_CLASS@@@Z; EtwpHeapRundown(ulong,_HEAP_RUNDOWN_CLASS)
0x180013add  xor     edx, edx
0x180013adf  cmp     [rsp+98h+var_68], dl
0x180013ae3  jz      short loc_180013B1A
0x180013ae5  call    cs:__imp_RtlGetCurrentServiceSessionId
0x180013aeb  test    eax, eax
0x180013aed  jz      short loc_180013B06
0x180013aef  mov     rax, gs:60h
0x180013af8  mov     rsi, [rax+90h]
0x180013aff  add     rsi, 230h
0x180013b06  movzx   eax, byte ptr [rsi]
0x180013b09  cmp     di, ax
0x180013b0c  jnz     short loc_180013B1A
0x180013b0e  mov     ecx, edi
0x180013b10  mov     edx, 1
0x180013b15  call    ?EtwpHeapRundown@@YAJKW4_HEAP_RUNDOWN_CLASS@@@Z; EtwpHeapRundown(ulong,_HEAP_RUNDOWN_CLASS)
0x180013b1a  test    r15b, r15b
0x180013b1d  jz      short loc_180013B5B
0x180013b1f  mov     rcx, [rbx+8]; unsigned __int64
0x180013b23  lea     rdx, [rsp+98h+var_60]; struct _PERFINFO_GROUPMASK *
0x180013b28  xorps   xmm0, xmm0
0x180013b2b  movups  [rsp+98h+var_60], xmm0
0x180013b30  movups  [rsp+98h+var_50], xmm0
0x180013b35  call    ?EtwpQueryGroupMaskForRundown@@YAX_KPEAU_PERFINFO_GROUPMASK@@@Z; EtwpQueryGroupMaskForRundown(unsigned __int64,_PERFINFO_GROUPMASK *)
0x180013b3a  call    IsEtwLogHeapRundownPresent
0x180013b3f  test    al, al
0x180013b41  jz      short loc_180013B5B
0x180013b43  test    dword ptr [rsp+98h+var_50+8], 1FFFFFFFh
0x180013b4b  jz      short loc_180013B5B
0x180013b4d  lea     rdx, [rsp+98h+var_60]
0x180013b52  movzx   ecx, di
0x180013b55  call    cs:__imp_EtwLogSysConfigRundown
0x180013b5b  mov     r8d, [rbx]
0x180013b5e  lea     rax, [rsp+98h+var_64]
0x180013b63  mov     [rsp+98h+var_70], rax
0x180013b68  mov     r9, rbx
0x180013b6b  mov     rdx, rbx
0x180013b6e  mov     [rsp+98h+var_78], r8d
0x180013b73  mov     ecx, 2
0x180013b78  call    NtTraceControl_0
0x180013b7d  test    eax, eax
0x180013b7f  jz      short loc_180013B9D
0x180013b81  mov     ecx, eax; Status
0x180013b83  call    RtlNtStatusToDosError_0
0x180013b88  jmp     short loc_180013B9D
0x180013b8a  mov     r9, r8
0x180013b8d  mov     ecx, 2
0x180013b92  mov     r8d, edx
0x180013b95  mov     rdx, rbx
0x180013b98  call    ?EtwpSendUmLogRequest@@YAKW4ETWTRACECONTROLCODE@@PEAU_WMI_LOGGER_INFORMATION@@KPEAU_EVENT_FILTER_DESCRIPTOR@@@Z; EtwpSendUmLogRequest(ETWTRACECONTROLCODE,_WMI_LOGGER_INFORMATION *,ulong,_EVENT_FILTER_DESCRIPTOR *)
0x180013b9d  mov     rcx, [rsp+98h+var_40]
0x180013ba2  xor     rcx, rsp; StackCookie
0x180013ba5  call    __security_check_cookie
0x180013baa  mov     rbx, [rsp+98h+arg_18]
0x180013bb2  add     rsp, 60h
0x180013bb6  pop     r15
0x180013bb8  pop     r14
0x180013bba  pop     r13
0x180013bbc  pop     r12
0x180013bbe  pop     rdi
0x180013bbf  pop     rsi
0x180013bc0  pop     rbp
0x180013bc1  retn
```
