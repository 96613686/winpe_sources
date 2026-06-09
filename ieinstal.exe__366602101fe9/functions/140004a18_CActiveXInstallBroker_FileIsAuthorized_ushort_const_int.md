# CActiveXInstallBroker::FileIsAuthorized(ushort const *,int)

- ea: `0x140004a18`
- end: `0x140004a99`
- name: `?FileIsAuthorized@CActiveXInstallBroker@@AEAAJPEBGH@Z`
- size: `129`
- prototype: `int(CActiveXInstallBroker *__hidden this, const unsigned __int16 *, int)`
- caller_count: `6`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1400049bc`
- `0x140004c88`
- `0x140004e20`
- `0x140005188`
- `0x140005630`
- `0x140005b10`

## callees

- `0x140004a18`
- `0x14000a4b0`
- `0x14000a5d4`
- `0x14000bc68`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x140004a73`
- `ole32!CoTaskMemFree` at `0x140004a73`

## pseudocode

```c
__int64 __fastcall CActiveXInstallBroker::FileIsAuthorized(CActiveXInstallBroker *this, const unsigned __int16 *a2)
{
  unsigned int v4; // edi
  __int64 v5; // rcx
  struct sFNAME *v6; // rsi
  int v7; // ebx
  LPVOID pv; // [rsp+48h] [rbp+20h] BYREF

  v4 = -2147024891;
  if ( !(unsigned int)IsFileAtIntegrityLevel(a2) )
  {
    v6 = (struct sFNAME *)*((_QWORD *)this + 16);
    pv = 0;
    if ( (int)WSZtoSZ(v5, a2, (char **)&pv) >= 0 )
    {
      v7 = IsInFileListA((const char *)pv, v6);
      CoTaskMemFree(pv);
      if ( v7 )
        return 0;
    }
  }
  return v4;
}

```

## disassembly

```asm
0x140004a18  mov     [rsp+arg_0], rbx
0x140004a1d  mov     [rsp+arg_8], rsi
0x140004a22  push    rdi
0x140004a23  sub     rsp, 20h
0x140004a27  mov     rsi, rcx
0x140004a2a  mov     rbx, rdx
0x140004a2d  mov     rcx, rdx; unsigned __int16 *
0x140004a30  mov     edi, 80070005h
0x140004a35  call    ?IsFileAtIntegrityLevel@@YAJPEBGH@Z; IsFileAtIntegrityLevel(ushort const *,int)
0x140004a3a  test    eax, eax
0x140004a3c  jnz     short loc_140004A86
0x140004a3e  mov     rsi, [rsi+80h]
0x140004a45  lea     r8, [rsp+28h+pv]; char **
0x140004a4a  mov     rdx, rbx; unsigned __int16 *
0x140004a4d  mov     [rsp+28h+pv], 0
0x140004a56  call    ?WSZtoSZ@@YAJIPEBGPEAPEAD@Z; WSZtoSZ(uint,ushort const *,char * *)
0x140004a5b  test    eax, eax
0x140004a5d  js      short loc_140004A86
0x140004a5f  mov     rcx, [rsp+28h+pv]; char *
0x140004a64  mov     rdx, rsi; struct sFNAME *
0x140004a67  call    ?IsInFileListA@@YAHPEBDPEAUsFNAME@@@Z; IsInFileListA(char const *,sFNAME *)
0x140004a6c  mov     rcx, [rsp+28h+pv]; pv
0x140004a71  mov     ebx, eax
0x140004a73  call    cs:__imp_CoTaskMemFree
0x140004a7a  nop     dword ptr [rax+rax+00h]
0x140004a7f  xor     ecx, ecx
0x140004a81  test    ebx, ebx
0x140004a83  cmovnz  edi, ecx
0x140004a86  mov     rbx, [rsp+28h+arg_0]
0x140004a8b  mov     eax, edi
0x140004a8d  mov     rsi, [rsp+28h+arg_8]
0x140004a92  add     rsp, 20h
0x140004a96  pop     rdi
0x140004a97  retn
```
