# EapDeleteUserDataInPersistentStore

- ea: `0x180025dbc`
- end: `0x180025e55`
- name: `EapDeleteUserDataInPersistentStore`
- size: `153`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180024860`

## callees

- `0x180004710`
- `0x180007f60`
- `0x18001c80c`
- `0x180025dbc`
- `0x1800280d0`

## pseudocode

```c
__int64 __fastcall EapDeleteUserDataInPersistentStore(__int64 *a1)
{
  __int64 v1; // rcx
  unsigned int v2; // edi
  __int64 v3; // rsi
  unsigned int v4; // ebx
  int IsUsingExplicitCreds; // eax
  __int64 v6; // rcx

  v1 = *a1;
  v2 = *(_DWORD *)(v1 + 20);
  v3 = v1 + 2384;
  v4 = MSMDeleteOneXUserProfile(v1, *(_QWORD *)(v1 + 2840));
  if ( v4 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 7), 43, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids, v2, v4);
  }
  else if ( byte_18003DF42 < 0 )
  {
    IsUsingExplicitCreds = SupplicantIsUsingExplicitCreds(v3);
    McTemplateU0qq_EtwEventWriteTransfer(v6, (__int64)FlushOnFailure, v2, IsUsingExplicitCreds);
  }
  return v4;
}

```

## disassembly

```asm
0x180025dbc  mov     [rsp+arg_0], rbx
0x180025dc1  mov     [rsp+arg_8], rsi
0x180025dc6  push    rdi
0x180025dc7  sub     rsp, 30h
0x180025dcb  mov     rcx, [rcx]
0x180025dce  mov     edi, [rcx+14h]
0x180025dd1  lea     rsi, [rcx+950h]
0x180025dd8  mov     rdx, [rsi+1C8h]
0x180025ddf  call    MSMDeleteOneXUserProfile
0x180025de4  mov     ebx, eax
0x180025de6  test    eax, eax
0x180025de8  jnz     short loc_180025E0E
0x180025dea  cmp     cs:byte_18003DF42, al
0x180025df0  jge     short loc_180025E43
0x180025df2  mov     rcx, rsi
0x180025df5  call    SupplicantIsUsingExplicitCreds
0x180025dfa  mov     r9d, eax
0x180025dfd  lea     rdx, FlushOnFailure
0x180025e04  mov     r8d, edi
0x180025e07  call    McTemplateU0qq_EtwEventWriteTransfer
0x180025e0c  jmp     short loc_180025E43
0x180025e0e  mov     rcx, cs:WPP_GLOBAL_Control
0x180025e15  lea     rax, WPP_GLOBAL_Control
0x180025e1c  cmp     rcx, rax
0x180025e1f  jz      short loc_180025E43
0x180025e21  test    byte ptr [rcx+44h], 1
0x180025e25  jz      short loc_180025E43
0x180025e27  mov     rcx, [rcx+38h]
0x180025e2b  lea     r8, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids
0x180025e32  mov     edx, 2Bh ; '+'
0x180025e37  mov     [rsp+38h+var_18], ebx
0x180025e3b  mov     r9d, edi
0x180025e3e  call    WPP_SF_dd
0x180025e43  mov     rsi, [rsp+38h+arg_8]
0x180025e48  mov     eax, ebx
0x180025e4a  mov     rbx, [rsp+38h+arg_0]
0x180025e4f  add     rsp, 30h
0x180025e53  pop     rdi
0x180025e54  retn
```
