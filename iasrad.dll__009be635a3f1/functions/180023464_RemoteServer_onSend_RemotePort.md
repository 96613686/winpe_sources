# RemoteServer::onSend(RemotePort)

- ea: `0x180023464`
- end: `0x18002369c`
- name: `?onSend@RemoteServer@@QEAAXVRemotePort@@@Z`
- size: `568`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180023af8`

## callees

- `0x1800094e4`
- `0x18001b004`
- `0x18001d31c`
- `0x180023464`
- `0x1800249ec`
- `0x18002819c`
- `0x18002e202`
- `0x18002e230`

## import_xrefs

- `msvcrt!free` at `0x180023669`
- `msvcrt!free` at `0x180023669`
- `KERNEL32!EnterCriticalSection` at `0x180023533`
- `KERNEL32!EnterCriticalSection` at `0x180023533`
- `KERNEL32!LeaveCriticalSection` at `0x180023660`
- `KERNEL32!LeaveCriticalSection` at `0x180023660`
- `WS2_32!__imp_ntohs` at `0x1800234b5`
- `WS2_32!__imp_ntohs` at `0x1800234b5`

## string_xrefs

- `0x180023599`: `Send packet to :Probation server: %S at [%S] : %d, set it to not-usable temporarily`

## pseudocode

```c
void __fastcall RemoteServer::onSend(__int64 a1, __int64 a2)
{
  char v4; // bp
  __int64 v5; // rbx
  __int64 v6[18]; // [rsp+50h] [rbp-C8h] BYREF

  memset_0(v6, 0, 0x82u);
  v4 = ntohs(*(_WORD *)(a2 + 26));
  if ( (int)ias_inet_htow((SOCKADDR *)(a2 + 24), v6) < 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
  {
    WppDbgPrint("Could not get string form of address");
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_c19ef362848c3e4b5773f2334e8422e1_Traceguids, "NPSRAD");
  }
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 384));
  ++*(_DWORD *)(a1 + 440);
  if ( *(_BYTE *)(a1 + 425) )
  {
    *(_BYTE *)(a1 + 424) = 0;
    v5 = 10000LL * *(unsigned int *)(a1 + 368);
    *(_QWORD *)(a1 + 432) = v5 + GetSystemTimeAsDWORDLONG();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    {
      WppDbgPrint("Send packet to :Probation server: %S at [%S] : %d, set it to not-usable temporarily");
LABEL_20:
      WPP_SF_sSSd(*((_QWORD *)WPP_GLOBAL_Control + 2), *(_QWORD *)(a1 + 40), (__int64)v6, v4);
    }
  }
  else if ( *(_BYTE *)(a1 + 424) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    {
      WppDbgPrint("Send packet to :Available server: %S at [%S] : %d");
      goto LABEL_20;
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
         && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
  {
    WppDbgPrint("Send packet to :Broadcastable server: %S at [%S] : %d");
    goto LABEL_20;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 384));
  free(*(void **)a2);
}

```

## disassembly

```asm
0x180023464  mov     [rsp+arg_10], rbx
0x180023469  mov     [rsp+arg_18], rbp
0x18002346e  push    rsi
0x18002346f  push    rdi
0x180023470  push    r12
0x180023472  push    r14
0x180023474  push    r15
0x180023476  sub     rsp, 0F0h
0x18002347d  mov     rax, cs:__security_cookie
0x180023484  xor     rax, rsp
0x180023487  mov     [rsp+118h+var_38], rax
0x18002348f  mov     r14, rdx
0x180023492  mov     rdi, rcx
0x180023495  xor     edx, edx; Val
0x180023497  mov     r8d, 82h; Size
0x18002349d  lea     rcx, [rsp+118h+var_C8]; void *
0x1800234a2  call    memset_0
0x1800234a7  mov     [rsp+118h+var_D8], 41h ; 'A'
0x1800234b0  movzx   ecx, word ptr [r14+1Ah]; netshort
0x1800234b5  call    cs:__imp_ntohs
0x1800234bb  movzx   ebp, ax
0x1800234be  lea     r8, [rsp+118h+var_D8]
0x1800234c3  lea     rdx, [rsp+118h+var_C8]; void *
0x1800234c8  lea     rcx, [r14+18h]; pSockaddr
0x1800234cc  call    ias_inet_htow
0x1800234d1  mov     r15d, 100h
0x1800234d7  lea     r12, WPP_GLOBAL_Control
0x1800234de  xor     ebx, ebx
0x1800234e0  test    eax, eax
0x1800234e2  jns     short loc_180023529
0x1800234e4  mov     rax, cs:WPP_GLOBAL_Control
0x1800234eb  cmp     rax, r12
0x1800234ee  jz      short loc_180023529
0x1800234f0  cmp     byte ptr [rax+19h], 2
0x1800234f4  jb      short loc_180023529
0x1800234f6  test    [rax+1Ch], r15d
0x1800234fa  jz      short loc_180023529
0x1800234fc  lea     rcx, aCouldNotGetStr; "Could not get string form of address"
0x180023503  call    WppDbgPrint
0x180023508  lea     edx, [rbx+17h]
0x18002350b  lea     r9, aNpsrad; "NPSRAD"
0x180023512  lea     r8, WPP_c19ef362848c3e4b5773f2334e8422e1_Traceguids
0x180023519  mov     rcx, cs:WPP_GLOBAL_Control
0x180023520  mov     rcx, [rcx+10h]
0x180023524  call    WPP_SF_s
0x180023529  lea     rsi, [rdi+180h]
0x180023530  mov     rcx, rsi; lpCriticalSection
0x180023533  call    cs:__imp_EnterCriticalSection
0x180023539  inc     dword ptr [rdi+1B8h]
0x18002353f  cmp     [rdi+1A9h], bl
0x180023545  jz      short loc_1800235AF
0x180023547  mov     [rdi+1A8h], bl
0x18002354d  mov     eax, [rdi+170h]
0x180023553  imul    rbx, rax, 2710h
0x18002355a  call    GetSystemTimeAsDWORDLONG
0x18002355f  add     rax, rbx
0x180023562  mov     [rdi+1B0h], rax
0x180023569  mov     rax, cs:WPP_GLOBAL_Control
0x180023570  cmp     rax, r12
0x180023573  jz      loc_18002365D
0x180023579  cmp     byte ptr [rax+19h], 2
0x18002357d  jb      loc_18002365D
0x180023583  test    [rax+1Ch], r15d
0x180023587  jz      loc_18002365D
0x18002358d  mov     r9d, ebp
0x180023590  lea     r8, [rsp+118h+var_C8]
0x180023595  mov     rdx, [rdi+28h]
0x180023599  lea     rcx, aSendPacketToPr; "Send packet to :Probation server: %S at"...
0x1800235a0  call    WppDbgPrint
0x1800235a5  mov     edx, 18h
0x1800235aa  jmp     loc_18002362F
0x1800235af  cmp     [rdi+1A8h], bl
0x1800235b5  jz      short loc_1800235FA
0x1800235b7  mov     rax, cs:WPP_GLOBAL_Control
0x1800235be  cmp     rax, r12
0x1800235c1  jz      loc_18002365D
0x1800235c7  cmp     byte ptr [rax+19h], 4
0x1800235cb  jb      loc_18002365D
0x1800235d1  test    [rax+1Ch], r15d
0x1800235d5  jz      loc_18002365D
0x1800235db  mov     r9d, ebp
0x1800235de  lea     r8, [rsp+118h+var_C8]
0x1800235e3  mov     rdx, [rdi+28h]
0x1800235e7  lea     rcx, aSendPacketToAv; "Send packet to :Available server: %S at"...
0x1800235ee  call    WppDbgPrint
0x1800235f3  mov     edx, 19h
0x1800235f8  jmp     short loc_18002362F
0x1800235fa  mov     rax, cs:WPP_GLOBAL_Control
0x180023601  cmp     rax, r12
0x180023604  jz      short loc_18002365D
0x180023606  cmp     byte ptr [rax+19h], 4
0x18002360a  jb      short loc_18002365D
0x18002360c  test    [rax+1Ch], r15d
0x180023610  jz      short loc_18002365D
0x180023612  mov     r9d, ebp
0x180023615  lea     r8, [rsp+118h+var_C8]
0x18002361a  mov     rdx, [rdi+28h]
0x18002361e  lea     rcx, aSendPacketToBr; "Send packet to :Broadcastable server: %"...
0x180023625  call    WppDbgPrint
0x18002362a  mov     edx, 1Ah
0x18002362f  mov     dword ptr [rsp+118h+var_E8], ebp; char
0x180023633  lea     rax, [rsp+118h+var_C8]
0x180023638  mov     [rsp+118h+var_F0], rax; __int64
0x18002363d  mov     rax, [rdi+28h]
0x180023641  mov     rcx, cs:WPP_GLOBAL_Control
0x180023648  mov     [rsp+118h+var_F8], rax; __int64
0x18002364d  lea     r8, WPP_c19ef362848c3e4b5773f2334e8422e1_Traceguids
0x180023654  mov     rcx, [rcx+10h]; LoggerHandle
0x180023658  call    WPP_SF_sSSd
0x18002365d  mov     rcx, rsi; lpCriticalSection
0x180023660  call    cs:__imp_LeaveCriticalSection
0x180023666  mov     rcx, [r14]; Block
0x180023669  call    cs:__imp_free
0x18002366f  nop
0x180023670  mov     rcx, [rsp+118h+var_38]
0x180023678  xor     rcx, rsp; StackCookie
0x18002367b  call    __security_check_cookie
0x180023680  lea     r11, [rsp+118h+var_28]
0x180023688  mov     rbx, [r11+40h]
0x18002368c  mov     rbp, [r11+48h]
0x180023690  mov     rsp, r11
0x180023693  pop     r15
0x180023695  pop     r14
0x180023697  pop     r12
0x180023699  pop     rdi
0x18002369a  pop     rsi
0x18002369b  retn
```
