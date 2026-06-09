# DsRolepWinlogonNotifyInit

- ea: `0x18000bbd4`
- end: `0x18000bca5`
- name: `DsRolepWinlogonNotifyInit`
- size: `209`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180003ff0`

## callees

- `0x18000ac50`
- `0x18000bbd4`
- `0x180020dbc`
- `0x18002c01e`

## import_xrefs

- `SYSNTFY!SysNotifyStartServer` at `0x18000bc77`
- `SYSNTFY!SysNotifyStartServer` at `0x18000bc77`

## string_xrefs

- `0x18000bbf3`: `vDCCloningUpdate`
- `0x18000bc1a`: `vDCCloningComplete`

## pseudocode

```c
__int64 DsRolepWinlogonNotifyInit()
{
  __int64 result; // rax
  int started; // eax
  unsigned int v2; // ebx
  _DWORD v3[2]; // [rsp+30h] [rbp-88h] BYREF
  __int64 (__fastcall *v4)(); // [rsp+38h] [rbp-80h]
  __int64 v5; // [rsp+C0h] [rbp+8h] BYREF

  v3[1] = 0;
  memset_0(v3, 0, 0x7Cu);
  v5 = 0;
  result = DsRolepCreatCloneEvent((void **)&ghMessageUpdateEvent, (__int64)L"vDCCloningUpdate");
  if ( !(_DWORD)result )
  {
    result = DsRolepCreatCloneEvent(&ghCloneCompleteEvent, (__int64)L"vDCCloningComplete");
    if ( !(_DWORD)result )
    {
      memset_0(v3, 0, 0x80u);
      v3[0] = 1;
      v4 = DsRolepWinlogonNotifyOnCreateSession;
      started = SysNotifyStartServer("NTDS", 128, v3, 0, &v5);
      v2 = started;
      if ( started )
        DsRolepLogPrintRoutine(1, "vDC Cloning: SysNotifyStartServer failed with error: 0x%x (%lu)\n", started, started);
      return v2;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000bbd4  push    rbx
0x18000bbd6  sub     rsp, 0B0h
0x18000bbdd  xor     eax, eax
0x18000bbdf  lea     rcx, [rsp+0B8h+var_88]; void *
0x18000bbe4  xor     edx, edx; Val
0x18000bbe6  mov     [rsp+0B8h+var_84], eax
0x18000bbea  lea     r8d, [rax+7Ch]; Size
0x18000bbee  call    memset_0
0x18000bbf3  lea     rdx, aVdccloningupda; "vDCCloningUpdate"
0x18000bbfa  mov     [rsp+0B8h+arg_0], 0
0x18000bc06  lea     rcx, ghMessageUpdateEvent
0x18000bc0d  call    DsRolepCreatCloneEvent
0x18000bc12  test    eax, eax
0x18000bc14  jnz     loc_18000BC9C
0x18000bc1a  lea     rdx, aVdccloningcomp; "vDCCloningComplete"
0x18000bc21  lea     rcx, ghCloneCompleteEvent
0x18000bc28  call    DsRolepCreatCloneEvent
0x18000bc2d  test    eax, eax
0x18000bc2f  jnz     short loc_18000BC9C
0x18000bc31  mov     ebx, 80h
0x18000bc36  lea     rcx, [rsp+0B8h+var_88]; void *
0x18000bc3b  mov     r8d, ebx; Size
0x18000bc3e  xor     edx, edx; Val
0x18000bc40  call    memset_0
0x18000bc45  lea     rax, DsRolepWinlogonNotifyOnCreateSession
0x18000bc4c  mov     [rsp+0B8h+var_88], 1
0x18000bc54  mov     [rsp+0B8h+var_80], rax
0x18000bc59  lea     r8, [rsp+0B8h+var_88]
0x18000bc5e  lea     rax, [rsp+0B8h+arg_0]
0x18000bc66  xor     r9d, r9d
0x18000bc69  mov     edx, ebx
0x18000bc6b  mov     [rsp+0B8h+var_98], rax
0x18000bc70  lea     rcx, aNtds_0; "NTDS"
0x18000bc77  call    cs:__imp_SysNotifyStartServer
0x18000bc7d  mov     ebx, eax
0x18000bc7f  test    eax, eax
0x18000bc81  jz      short loc_18000BC9A
0x18000bc83  mov     r9d, eax
0x18000bc86  lea     rdx, aVdcCloningSysn; "vDC Cloning: SysNotifyStartServer faile"...
0x18000bc8d  mov     r8d, eax
0x18000bc90  mov     ecx, 1
0x18000bc95  call    DsRolepLogPrintRoutine
0x18000bc9a  mov     eax, ebx
0x18000bc9c  add     rsp, 0B0h
0x18000bca3  pop     rbx
0x18000bca4  retn
```
