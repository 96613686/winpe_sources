# ProcessRdmaRecvCompletion

- ea: `0x18004fd1c`
- end: `0x18004fe37`
- name: `ProcessRdmaRecvCompletion`
- size: `283`
- prototype: `__int64 __fastcall(PVOID CompletionContext)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800485dc`

## callees

- `0x180038a20`
- `0x180038c40`
- `0x18003cdc8`
- `0x180042128`
- `0x18004fd1c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004fdb5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004fddf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004fe21`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004fdb5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004fddf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004fe21`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004fd31`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004fd31`

## pseudocode

```c
void __fastcall ProcessRdmaRecvCompletion(char *CompletionContext, unsigned int a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rsi
  _QWORD *v5; // rax
  _QWORD *v6; // rbx
  unsigned int v7; // r8d

  v2 = (struct _RTL_CRITICAL_SECTION *)(CompletionContext + 48);
  EnterCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
  if ( *((_DWORD *)CompletionContext + 34) || *((_DWORD *)CompletionContext + 201) )
  {
    LeaveCriticalSection(v2);
  }
  else
  {
    v5 = CompletionContext + 320;
    do
    {
      v5 = (_QWORD *)*v5;
      v6 = v5 - 2;
    }
    while ( *((_DWORD *)v5 + 23) );
    v7 = *(_DWORD *)(v6[15] + 80LL);
    if ( a2 <= v7 )
    {
      *((_DWORD *)v6 + 10) += a2;
      *((_DWORD *)v6 + 27) = 1;
      *((_DWORD *)v6 + 8) = 0;
      LeaveCriticalSection(v2);
      if ( (BYTE1(xmmword_180063D60) & 0x10) != 0 )
        WPP_SF_qD(1036, 18, WPP_c3b0ca9683b83d20c098afa417d2e04a_Traceguids, v6, *((_DWORD *)v6 + 10));
      CheckPendingAppRecvs(CompletionContext);
    }
    else
    {
      if ( (xmmword_180063D60 & 2) != 0 )
        WPP_SF_ddq(1025, 17, WPP_c3b0ca9683b83d20c098afa417d2e04a_Traceguids, a2, v7, v6);
      *((_DWORD *)v6 + 27) = 1;
      *((_DWORD *)v6 + 8) = 0;
      LeaveCriticalSection(v2);
      AbortSanConnection(CompletionContext);
    }
  }
}

```

## disassembly

```asm
0x18004fd1c  push    rbx
0x18004fd1e  push    rbp
0x18004fd1f  push    rsi
0x18004fd20  push    rdi
0x18004fd21  sub     rsp, 38h
0x18004fd25  lea     rsi, [rcx+30h]
0x18004fd29  mov     rdi, rcx
0x18004fd2c  mov     rcx, rsi; lpCriticalSection
0x18004fd2f  mov     ebp, edx
0x18004fd31  call    cs:__imp_EnterCriticalSection
0x18004fd38  nop     dword ptr [rax+rax+00h]
0x18004fd3d  cmp     dword ptr [rdi+88h], 0
0x18004fd44  jnz     loc_18004FE1E
0x18004fd4a  cmp     dword ptr [rdi+324h], 0
0x18004fd51  jnz     loc_18004FE1E
0x18004fd57  lea     rax, [rdi+140h]
0x18004fd5e  mov     rax, [rax]
0x18004fd61  lea     rbx, [rax-10h]
0x18004fd65  cmp     dword ptr [rbx+6Ch], 0
0x18004fd69  jnz     short loc_18004FD5E
0x18004fd6b  mov     rax, [rbx+78h]
0x18004fd6f  mov     r8d, [rax+50h]
0x18004fd73  cmp     ebp, r8d
0x18004fd76  jbe     short loc_18004FDCB
0x18004fd78  test    byte ptr cs:xmmword_180063D60, 2
0x18004fd7f  jz      short loc_18004FDA4
0x18004fd81  mov     [rsp+58h+var_30], rbx
0x18004fd86  mov     edx, 11h
0x18004fd8b  mov     [rsp+58h+var_38], r8d
0x18004fd90  mov     ecx, 401h
0x18004fd95  lea     r8, WPP_c3b0ca9683b83d20c098afa417d2e04a_Traceguids
0x18004fd9c  mov     r9d, ebp
0x18004fd9f  call    WPP_SF_ddq
0x18004fda4  mov     rcx, rsi; lpCriticalSection
0x18004fda7  mov     dword ptr [rbx+6Ch], 1
0x18004fdae  mov     dword ptr [rbx+20h], 0
0x18004fdb5  call    cs:__imp_LeaveCriticalSection
0x18004fdbc  nop     dword ptr [rax+rax+00h]
0x18004fdc1  mov     rcx, rdi
0x18004fdc4  call    AbortSanConnection
0x18004fdc9  jmp     short loc_18004FE2D
0x18004fdcb  add     [rbx+28h], ebp
0x18004fdce  mov     rcx, rsi; lpCriticalSection
0x18004fdd1  mov     dword ptr [rbx+6Ch], 1
0x18004fdd8  mov     dword ptr [rbx+20h], 0
0x18004fddf  call    cs:__imp_LeaveCriticalSection
0x18004fde6  nop     dword ptr [rax+rax+00h]
0x18004fdeb  test    byte ptr cs:xmmword_180063D60+1, 10h
0x18004fdf2  jz      short loc_18004FE14
0x18004fdf4  mov     eax, [rbx+28h]
0x18004fdf7  lea     r8, WPP_c3b0ca9683b83d20c098afa417d2e04a_Traceguids
0x18004fdfe  mov     edx, 12h
0x18004fe03  mov     [rsp+58h+var_38], eax
0x18004fe07  mov     ecx, 40Ch
0x18004fe0c  mov     r9, rbx
0x18004fe0f  call    WPP_SF_qD
0x18004fe14  mov     rcx, rdi; CompletionContext
0x18004fe17  call    CheckPendingAppRecvs
0x18004fe1c  jmp     short loc_18004FE2D
0x18004fe1e  mov     rcx, rsi; lpCriticalSection
0x18004fe21  call    cs:__imp_LeaveCriticalSection
0x18004fe28  nop     dword ptr [rax+rax+00h]
0x18004fe2d  add     rsp, 38h
0x18004fe31  pop     rdi
0x18004fe32  pop     rsi
0x18004fe33  pop     rbp
0x18004fe34  pop     rbx
0x18004fe35  retn
```
