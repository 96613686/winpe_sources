# UserSecurityContext::InitializeCertInfo(bool)

- ea: `0x1800174e0`
- end: `0x180017535`
- name: `?InitializeCertInfo@UserSecurityContext@@UEAAJ_N@Z`
- size: `85`
- prototype: `__int64 __fastcall(UserSecurityContext *__hidden this, bool)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180013c74`
- `0x180016944`
- `0x180016f30`
- `0x1800174e0`

## pseudocode

```c
__int64 __fastcall UserSecurityContext::InitializeCertInfo(UserSecurityContext *this, unsigned __int8 a2)
{
  int v2; // eax
  unsigned __int8 *v4; // rdx
  int v5; // eax
  unsigned int v6; // ebx

  v2 = a2;
  v4 = (unsigned __int8 *)*((_QWORD *)this + 2);
  if ( v4 )
    v5 = UserSecurityContext::HandleExternalCert(this, v4, *((_DWORD *)this + 12));
  else
    v5 = RTSecurityContextBase::HandleInternalCert(this, v2);
  *((_DWORD *)this + 17) = v5;
  v6 = v5;
  if ( v5 < 0 )
    LogMsgHR(v5, (wchar_t *)L"rt/rtsecctx", 0x15Eu);
  return v6;
}

```

## disassembly

```asm
0x1800174e0  mov     [rsp+arg_0], rbx
0x1800174e5  push    rdi
0x1800174e6  sub     rsp, 20h
0x1800174ea  movzx   eax, dl
0x1800174ed  mov     rdi, rcx
0x1800174f0  mov     rdx, [rcx+10h]; unsigned __int8 *
0x1800174f4  test    rdx, rdx
0x1800174f7  jnz     short loc_180017502
0x1800174f9  mov     edx, eax; int
0x1800174fb  call    ?HandleInternalCert@RTSecurityContextBase@@IEAAJH@Z; RTSecurityContextBase::HandleInternalCert(int)
0x180017500  jmp     short loc_18001750B
0x180017502  mov     r8d, [rcx+30h]; unsigned int
0x180017506  call    ?HandleExternalCert@UserSecurityContext@@AEAAJPEAEK@Z; UserSecurityContext::HandleExternalCert(uchar *,ulong)
0x18001750b  mov     [rdi+44h], eax
0x18001750e  mov     ebx, eax
0x180017510  test    eax, eax
0x180017512  jns     short loc_180017528
0x180017514  mov     r8d, 15Eh; unsigned __int16
0x18001751a  lea     rdx, aRtRtsecctx; "rt/rtsecctx"
0x180017521  mov     ecx, eax; int
0x180017523  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180017528  mov     eax, ebx
0x18001752a  mov     rbx, [rsp+28h+arg_0]
0x18001752f  add     rsp, 20h
0x180017533  pop     rdi
0x180017534  retn
```
