# CUmRdp::IsSystemToken(void *)

- ea: `0x140016bcc`
- end: `0x140016c55`
- name: `?IsSystemToken@CUmRdp@@IEAAHPEAX@Z`
- size: `137`
- prototype: `int(CUmRdp *__hidden this, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140016b18`

## callees

- `0x140004b1c`
- `0x140005704`
- `0x140016bcc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140016c14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140016c14`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x140016beb`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x140016beb`

## pseudocode

```c
__int64 __fastcall CUmRdp::IsSystemToken(CUmRdp *this, void *a2)
{
  void *v3; // rdx
  unsigned int v4; // edi
  DWORD LastError; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  WINBOOL IsMember; // [rsp+40h] [rbp+8h] BYREF

  v3 = (void *)*((_QWORD *)this + 1);
  v4 = 0;
  IsMember = 0;
  if ( CheckTokenMembership(a2, v3, &IsMember) )
  {
    return (unsigned int)IsMember;
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    LastError = GetLastError();
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      13,
      WPP_e1878ade8ac733f4c5d20ac7d29e2f6b_Traceguids,
      CurrentThreadActivityIdPrefix,
      LastError);
  }
  return v4;
}

```

## disassembly

```asm
0x140016bcc  mov     [rsp+arg_8], rbx
0x140016bd1  push    rdi
0x140016bd2  sub     rsp, 30h
0x140016bd6  mov     rax, rdx
0x140016bd9  lea     r8, [rsp+38h+IsMember]; IsMember
0x140016bde  mov     rdx, [rcx+8]; SidToCheck
0x140016be2  xor     edi, edi
0x140016be4  mov     rcx, rax; TokenHandle
0x140016be7  mov     [rsp+38h+IsMember], edi
0x140016beb  call    cs:__imp_CheckTokenMembership
0x140016bf1  test    eax, eax
0x140016bf3  jnz     short loc_140016C44
0x140016bf5  mov     rax, cs:WPP_GLOBAL_Control
0x140016bfc  lea     rcx, WPP_GLOBAL_Control
0x140016c03  cmp     rax, rcx
0x140016c06  jz      short loc_140016C48
0x140016c08  test    byte ptr [rax+1Ch], 1
0x140016c0c  jz      short loc_140016C48
0x140016c0e  cmp     byte ptr [rax+19h], 2
0x140016c12  jb      short loc_140016C48
0x140016c14  call    cs:__imp_GetLastError
0x140016c1a  mov     ebx, eax
0x140016c1c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140016c21  mov     rcx, cs:WPP_GLOBAL_Control
0x140016c28  lea     edx, [rdi+0Dh]
0x140016c2b  mov     r9d, eax
0x140016c2e  mov     [rsp+38h+var_18], ebx
0x140016c32  lea     r8, WPP_e1878ade8ac733f4c5d20ac7d29e2f6b_Traceguids
0x140016c39  mov     rcx, [rcx+10h]
0x140016c3d  call    WPP_SF_Dd
0x140016c42  jmp     short loc_140016C48
0x140016c44  mov     edi, [rsp+38h+IsMember]
0x140016c48  mov     rbx, [rsp+38h+arg_8]
0x140016c4d  mov     eax, edi
0x140016c4f  add     rsp, 30h
0x140016c53  pop     rdi
0x140016c54  retn
```
