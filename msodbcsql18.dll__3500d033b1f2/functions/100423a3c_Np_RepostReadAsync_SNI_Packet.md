# Np::RepostReadAsync(SNI_Packet *)

- ea: `0x100423a3c`
- end: `0x100423c11`
- name: `?RepostReadAsync@Np@@AEAAKPEAVSNI_Packet@@@Z`
- size: `469`
- prototype: `unsigned int __fastcall(Np *__hidden this, LPOVERLAPPED lpOverlapped)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, loader_planting`

## callers

- `0x100423110`

## callees

- `0x100423a3c`
- `0x10043a7c4`
- `0x10043a930`
- `0x10043af84`
- `0x10043b378`
- `0x100545d84`
- `0x1005468d8`
- `0x100546aa8`

## import_xrefs

- `KERNEL32!GetLastError` at `0x100423b12`
- `KERNEL32!GetLastError` at `0x100423b12`
- `KERNEL32!ReadFile` at `0x100423aff`
- `KERNEL32!ReadFile` at `0x100423aff`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Np::RepostReadAsync(HANDLE *this, LPOVERLAPPED lpOverlapped)
{
  char *v4; // rsi
  unsigned int v5; // ebx
  wchar_t *v6; // r8
  __int64 v7; // rdx
  DWORD LastError; // eax
  __int64 v10; // [rsp+58h] [rbp+10h] BYREF

  v10 = -1;
  if ( (bidGblFlags & 0x20004) == 0x20004 && off_1005E7A38[0] )
    bidScopeEnterW(&v10, off_1005E7A38[0], *((unsigned int *)this + 11));
  v4 = (char *)lpOverlapped[2].Pointer + LODWORD(lpOverlapped[3].Internal);
  lpOverlapped->Offset = 0;
  lpOverlapped->OffsetHigh = 0;
  if ( !SNI::detail::Transport::FAddHandleRef((SNI::detail::Transport *)this) )
  {
    v5 = 6;
    if ( (bidGblFlags & 2) != 0 && off_1005E4E78[0] )
    {
      SniErrorIdFromStringId(0xC3B4u);
      v6 = off_1005E4E78[0];
      v7 = 1014784;
LABEL_14:
      bidTraceW(0, v7, v6, *((unsigned int *)this + 18));
      goto LABEL_15;
    }
    goto LABEL_15;
  }
  if ( !ReadFile(this[8], v4, HIDWORD(lpOverlapped[2].hEvent) - LODWORD(lpOverlapped[2].hEvent), 0, lpOverlapped) )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError != 997 && LastError != 234 )
    {
      SNI::detail::Transport::ReleaseHandleRef((SNI::detail::Transport *)this);
      if ( (bidGblFlags & 2) != 0 && off_1005E4E80[0] )
      {
        SniErrorIdFromStringId(0xC3B4u);
        v6 = off_1005E4E80[0];
        v7 = 1042432;
        goto LABEL_14;
      }
LABEL_15:
      SNISetLastError(*((unsigned int *)this + 18), v5, 50100);
      if ( (bidGblFlags & 0x20002) == 0x20002 && off_1005E4E90[0] )
        bidTraceW(0, 1056768, off_1005E4E90[0], v5);
      goto LABEL_22;
    }
  }
  SNI::detail::Transport::ReleaseHandleRef((SNI::detail::Transport *)this);
  if ( (bidGblFlags & 0x20002) == 0x20002 && off_1005E4E88[0] )
    bidTraceW(0, 1052672, off_1005E4E88[0], 997);
  v5 = 997;
LABEL_22:
  _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)&v10);
  return v5;
}

```

## disassembly

```asm
0x100423a3c  mov     r11, rsp
0x100423a3f  push    rdi
0x100423a40  sub     rsp, 40h
0x100423a44  mov     qword ptr [r11-18h], 0FFFFFFFFFFFFFFFEh
0x100423a4c  mov     [r11+8], rbx
0x100423a50  mov     [r11+18h], rsi
0x100423a54  mov     rbx, rdx
0x100423a57  mov     rdi, rcx
0x100423a5a  or      qword ptr [r11+10h], 0FFFFFFFFFFFFFFFFh
0x100423a5f  mov     eax, cs:_bidGblFlags
0x100423a65  mov     ecx, 20004h
0x100423a6a  and     eax, ecx
0x100423a6c  cmp     eax, ecx
0x100423a6e  jnz     short loc_100423A93
0x100423a70  mov     rax, cs:off_1005E7A38; "<Np::RepostReadAsync|API|SNI> %u#, pPac"...
0x100423a77  test    rax, rax
0x100423a7a  jz      short loc_100423A93
0x100423a7c  mov     r9, rdx
0x100423a7f  mov     r8d, [rdi+2Ch]
0x100423a83  mov     rdx, cs:off_1005E7A38; "<Np::RepostReadAsync|API|SNI> %u#, pPac"...
0x100423a8a  lea     rcx, [r11+10h]
0x100423a8e  call    _bidScopeEnterW
0x100423a93  mov     esi, [rbx+60h]
0x100423a96  add     rsi, [rbx+50h]
0x100423a9a  and     dword ptr [rbx+10h], 0
0x100423a9e  and     dword ptr [rbx+14h], 0
0x100423aa2  mov     rcx, rdi; this
0x100423aa5  call    ?FAddHandleRef@Transport@detail@SNI@@IEAA_NXZ; SNI::detail::Transport::FAddHandleRef(void)
0x100423aaa  test    al, al
0x100423aac  jnz     short loc_100423AE8
0x100423aae  mov     ebx, 6
0x100423ab3  test    byte ptr cs:_bidGblFlags, 2
0x100423aba  jz      loc_100423B73
0x100423ac0  mov     rax, cs:off_1005E4E78; "<Np::RepostReadAsync|ERR|SNI> ProviderN"...
0x100423ac7  test    rax, rax
0x100423aca  jz      loc_100423B73
0x100423ad0  mov     ecx, 0C3B4h; unsigned int
0x100423ad5  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x100423ada  mov     r8, cs:off_1005E4E78; "<Np::RepostReadAsync|ERR|SNI> ProviderN"...
0x100423ae1  mov     edx, 0F7C00h
0x100423ae6  jmp     short loc_100423B60
0x100423ae8  mov     r8d, [rbx+5Ch]
0x100423aec  sub     r8d, [rbx+58h]; nNumberOfBytesToRead
0x100423af0  mov     [rsp+48h+lpOverlapped], rbx; lpOverlapped
0x100423af5  xor     r9d, r9d; lpNumberOfBytesRead
0x100423af8  mov     rdx, rsi; lpBuffer
0x100423afb  mov     rcx, [rdi+40h]; hFile
0x100423aff  call    cs:__imp_ReadFile
0x100423b05  mov     esi, 3E5h
0x100423b0a  test    eax, eax
0x100423b0c  jnz     loc_100423BB8
0x100423b12  call    cs:__imp_GetLastError
0x100423b18  mov     ebx, eax
0x100423b1a  cmp     eax, esi
0x100423b1c  jz      loc_100423BB8
0x100423b22  cmp     eax, 0EAh
0x100423b27  jz      loc_100423BB8
0x100423b2d  mov     rcx, rdi; this
0x100423b30  call    ?ReleaseHandleRef@Transport@detail@SNI@@IEAAXXZ; SNI::detail::Transport::ReleaseHandleRef(void)
0x100423b35  test    byte ptr cs:_bidGblFlags, 2
0x100423b3c  jz      short loc_100423B73
0x100423b3e  mov     rax, cs:off_1005E4E80; "<Np::RepostReadAsync|ERR|SNI> ProviderN"...
0x100423b45  test    rax, rax
0x100423b48  jz      short loc_100423B73
0x100423b4a  mov     ecx, 0C3B4h; unsigned int
0x100423b4f  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x100423b54  mov     r8, cs:off_1005E4E80; "<Np::RepostReadAsync|ERR|SNI> ProviderN"...
0x100423b5b  mov     edx, 0FE800h
0x100423b60  mov     [rsp+48h+var_20], ebx
0x100423b64  mov     dword ptr [rsp+48h+lpOverlapped], eax
0x100423b68  mov     r9d, [rdi+48h]
0x100423b6c  xor     ecx, ecx
0x100423b6e  call    _bidTraceW
0x100423b73  mov     r8d, 0C3B4h
0x100423b79  mov     edx, ebx
0x100423b7b  mov     ecx, [rdi+48h]
0x100423b7e  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x100423b83  mov     eax, cs:_bidGblFlags
0x100423b89  mov     ecx, 20002h
0x100423b8e  and     eax, ecx
0x100423b90  cmp     eax, ecx
0x100423b92  jnz     short loc_100423BF5
0x100423b94  mov     rax, cs:off_1005E4E90; "<Np::RepostReadAsync|RET|SNI> %d{WINERR"...
0x100423b9b  test    rax, rax
0x100423b9e  jz      short loc_100423BF5
0x100423ba0  mov     r9d, ebx
0x100423ba3  mov     r8, cs:off_1005E4E90; "<Np::RepostReadAsync|RET|SNI> %d{WINERR"...
0x100423baa  mov     edx, 102000h
0x100423baf  xor     ecx, ecx
0x100423bb1  call    _bidTraceW
0x100423bb6  jmp     short loc_100423BF5
0x100423bb8  mov     rcx, rdi; this
0x100423bbb  call    ?ReleaseHandleRef@Transport@detail@SNI@@IEAAXXZ; SNI::detail::Transport::ReleaseHandleRef(void)
0x100423bc0  mov     eax, cs:_bidGblFlags
0x100423bc6  mov     ecx, 20002h
0x100423bcb  and     eax, ecx
0x100423bcd  cmp     eax, ecx
0x100423bcf  jnz     short loc_100423BF3
0x100423bd1  mov     rax, cs:off_1005E4E88; "<Np::RepostReadAsync|RET|SNI> %d{WINERR"...
0x100423bd8  test    rax, rax
0x100423bdb  jz      short loc_100423BF3
0x100423bdd  mov     r9d, esi
0x100423be0  mov     r8, cs:off_1005E4E88; "<Np::RepostReadAsync|RET|SNI> %d{WINERR"...
0x100423be7  mov     edx, 101000h
0x100423bec  xor     ecx, ecx
0x100423bee  call    _bidTraceW
0x100423bf3  mov     ebx, esi
0x100423bf5  lea     rcx, [rsp+48h+arg_8]; this
0x100423bfa  call    ?Out@_bidCAutoScopeAnchor@@QEAAHXZ; _bidCAutoScopeAnchor::Out(void)
0x100423bff  mov     eax, ebx
0x100423c01  mov     rbx, [rsp+48h+arg_0]
0x100423c06  mov     rsi, [rsp+48h+arg_10]
0x100423c0b  add     rsp, 40h
0x100423c0f  pop     rdi
0x100423c10  retn
```
