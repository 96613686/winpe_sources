# RevertToLocalSystem

- ea: `0x180010fac`
- end: `0x1800110b1`
- name: `RevertToLocalSystem`
- size: `261`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180011208`
- `0x180012568`
- `0x180013350`

## callees

- `0x18000af80`
- `0x18000b250`
- `0x180010fac`
- `0x1800110b8`

## import_xrefs

- `ntdll!NtSetInformationThread` at `0x180010ff4`
- `ntdll!NtSetInformationThread` at `0x180010ff4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800110a0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800110a0`

## string_xrefs

- `0x18001104b`: `onecore\ds\security\cryptoapi\ncrypt\storage\helpers.c`
- `0x180011086`: `onecore\ds\security\cryptoapi\ncrypt\storage\helpers.c`

## pseudocode

```c
__int64 __fastcall RevertToLocalSystem(_QWORD *a1)
{
  int v2; // eax
  int v3; // ebx
  int v4; // r8d
  void *v5; // rcx
  void *v7; // [rsp+58h] [rbp+10h] BYREF
  __int64 ThreadInformation; // [rsp+60h] [rbp+18h] BYREF

  v7 = 0;
  ThreadInformation = 0;
  v2 = OpenCallerToken(0xEu, &v7);
  if ( v2 )
  {
    if ( v2 > 0 )
      v3 = (unsigned __int16)v2 | 0xC0070000;
    else
      v3 = v2;
    DebugTraceError((unsigned int)v2, "dwStatus", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\helpers.c", 309);
  }
  else
  {
    v3 = NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &ThreadInformation, 8u);
    if ( v3 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\helpers.c",
          v4,
          (unsigned int)"ntStatus",
          v3,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\helpers.c",
          69);
      v5 = v7;
    }
    else
    {
      v5 = 0;
      *a1 = v7;
    }
    if ( v5 )
      CloseHandle(v5);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180010fac  mov     rax, rsp
0x180010faf  mov     [rax+8], rbx
0x180010fb3  push    rdi
0x180010fb4  sub     rsp, 40h
0x180010fb8  mov     rdi, rcx
0x180010fbb  mov     qword ptr [rax+10h], 0
0x180010fc3  mov     ecx, 0Eh; DesiredAccess
0x180010fc8  mov     qword ptr [rax+18h], 0
0x180010fd0  lea     rdx, [rax+10h]
0x180010fd4  call    OpenCallerToken
0x180010fd9  test    eax, eax
0x180010fdb  jnz     loc_180011071
0x180010fe1  lea     r9d, [rax+8]; ThreadInformationLength
0x180010fe5  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180010fec  lea     r8, [rsp+48h+ThreadInformation]; ThreadInformation
0x180010ff1  lea     edx, [rax+5]; ThreadInformationClass
0x180010ff4  call    cs:__imp_NtSetInformationThread
0x180010ffb  nop     dword ptr [rax+rax+00h]
0x180011000  mov     ebx, eax
0x180011002  test    eax, eax
0x180011004  js      short loc_180011027
0x180011006  mov     rax, [rsp+48h+arg_8]
0x18001100b  xor     ecx, ecx; hObject
0x18001100d  mov     [rdi], rax
0x180011010  test    rcx, rcx
0x180011013  jnz     loc_1800110A0
0x180011019  mov     eax, ebx
0x18001101b  mov     rbx, [rsp+48h+arg_0]
0x180011020  add     rsp, 40h
0x180011024  pop     rdi
0x180011025  retn
0x180011027  mov     rcx, cs:WPP_GLOBAL_Control
0x18001102e  lea     rax, WPP_GLOBAL_Control
0x180011035  cmp     rcx, rax
0x180011038  jz      short loc_180011040
0x18001103a  test    byte ptr [rcx+1Ch], 1
0x18001103e  jnz     short loc_180011047
0x180011040  mov     rcx, [rsp+48h+arg_8]
0x180011045  jmp     short loc_180011010
0x180011047  mov     rcx, [rcx+10h]
0x18001104b  lea     rdx, aOnecoreDsSecur_14; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180011052  mov     [rsp+48h+var_18], 145h
0x18001105a  lea     r9, aNtstatus; "ntStatus"
0x180011061  mov     [rsp+48h+var_20], rdx
0x180011066  mov     [rsp+48h+var_28], ebx
0x18001106a  call    WPP_SF_sDsd
0x18001106f  jmp     short loc_180011040
0x180011071  jg      short loc_180011077
0x180011073  mov     ebx, eax
0x180011075  jmp     short loc_180011080
0x180011077  movzx   ebx, ax
0x18001107a  or      ebx, 0C0070000h
0x180011080  mov     r9d, 135h
0x180011086  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001108d  lea     rdx, aDwstatus; "dwStatus"
0x180011094  mov     ecx, eax
0x180011096  call    DebugTraceError
0x18001109b  jmp     loc_180011019
0x1800110a0  call    cs:__imp_CloseHandle
0x1800110a7  nop     dword ptr [rax+rax+00h]
0x1800110ac  jmp     loc_180011019
```
