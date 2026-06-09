# CheckReadvertiseFirstSend

- ea: `0x180045e74`
- end: `0x180045f4a`
- name: `CheckReadvertiseFirstSend`
- size: `214`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800485dc`

## callees

- `0x180024dd4`
- `0x180038ac8`
- `0x180045e74`
- `0x180050074`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180045ee3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180045f34`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180045ee3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180045f34`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180045e8f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180045f21`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180045e8f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180045f21`

## pseudocode

```c
void __fastcall CheckReadvertiseFirstSend(char *CompletionContext)
{
  struct _RTL_CRITICAL_SECTION *v1; // rdi
  __int64 v3; // rbx
  unsigned int v4; // ebp
  int v5; // edx
  __int64 v6; // rcx
  __int64 v7; // r8
  unsigned int v8; // [rsp+60h] [rbp+8h] BYREF

  v1 = (struct _RTL_CRITICAL_SECTION *)(CompletionContext + 48);
  v8 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
  v3 = *((_QWORD *)CompletionContext + 50);
  if ( (char *)v3 != CompletionContext + 400 && (*(_DWORD *)(v3 + 76) & 1) == 0 && !*(_BYTE *)(v3 + 114) )
  {
    if ( *(_DWORD *)(v3 + 96) )
    {
      if ( !*(_QWORD *)(v3 + 120) )
      {
        v4 = *(_DWORD *)(v3 + 64) - *(_DWORD *)(v3 + 68);
        if ( (unsigned int)UseRdma(v4) )
        {
          *(_DWORD *)(v3 + 76) = v5 & 0xFFFFFFFB;
          LeaveCriticalSection(v1);
          if ( (BYTE1(xmmword_180063D60) & 0x10) != 0 )
            WPP_SF_Dd(v6, 194, v7, *(unsigned int *)(v3 + 76), v4);
          SendLargeSendFirstMsg(CompletionContext, v3 - 16, 0, &v8);
          EnterCriticalSection(v1);
          *(_BYTE *)(v3 + 114) = 1;
        }
      }
    }
  }
  LeaveCriticalSection(v1);
}

```

## disassembly

```asm
0x180045e74  push    rbx
0x180045e76  push    rbp
0x180045e77  push    rsi
0x180045e78  push    rdi
0x180045e79  sub     rsp, 38h
0x180045e7d  lea     rdi, [rcx+30h]
0x180045e81  mov     [rsp+58h+arg_0], 0
0x180045e89  mov     rsi, rcx
0x180045e8c  mov     rcx, rdi; lpCriticalSection
0x180045e8f  call    cs:__imp_EnterCriticalSection
0x180045e96  nop     dword ptr [rax+rax+00h]
0x180045e9b  lea     rax, [rsi+190h]
0x180045ea2  mov     rbx, [rax]
0x180045ea5  cmp     rbx, rax
0x180045ea8  jz      loc_180045F31
0x180045eae  mov     edx, [rbx+4Ch]
0x180045eb1  test    dl, 1
0x180045eb4  jnz     short loc_180045F31
0x180045eb6  cmp     byte ptr [rbx+72h], 0
0x180045eba  jnz     short loc_180045F31
0x180045ebc  cmp     dword ptr [rbx+60h], 0
0x180045ec0  jz      short loc_180045F31
0x180045ec2  cmp     qword ptr [rbx+78h], 0
0x180045ec7  jnz     short loc_180045F31
0x180045ec9  mov     ebp, [rbx+40h]
0x180045ecc  sub     ebp, [rbx+44h]
0x180045ecf  mov     ecx, ebp
0x180045ed1  call    UseRdma
0x180045ed6  test    eax, eax
0x180045ed8  jz      short loc_180045F31
0x180045eda  and     edx, 0FFFFFFFBh
0x180045edd  mov     rcx, rdi; lpCriticalSection
0x180045ee0  mov     [rbx+4Ch], edx
0x180045ee3  call    cs:__imp_LeaveCriticalSection
0x180045eea  nop     dword ptr [rax+rax+00h]
0x180045eef  test    byte ptr cs:xmmword_180063D60+1, 10h
0x180045ef6  jz      short loc_180045F0A
0x180045ef8  mov     r9d, [rbx+4Ch]
0x180045efc  mov     edx, 0C2h
0x180045f01  mov     [rsp+58h+var_38], ebp
0x180045f05  call    WPP_SF_Dd
0x180045f0a  lea     r9, [rsp+58h+arg_0]
0x180045f0f  xor     r8d, r8d
0x180045f12  lea     rdx, [rbx-10h]
0x180045f16  mov     rcx, rsi; CompletionContext
0x180045f19  call    SendLargeSendFirstMsg
0x180045f1e  mov     rcx, rdi; lpCriticalSection
0x180045f21  call    cs:__imp_EnterCriticalSection
0x180045f28  nop     dword ptr [rax+rax+00h]
0x180045f2d  mov     byte ptr [rbx+72h], 1
0x180045f31  mov     rcx, rdi; lpCriticalSection
0x180045f34  call    cs:__imp_LeaveCriticalSection
0x180045f3b  nop     dword ptr [rax+rax+00h]
0x180045f40  add     rsp, 38h
0x180045f44  pop     rdi
0x180045f45  pop     rsi
0x180045f46  pop     rbp
0x180045f47  pop     rbx
0x180045f48  retn
```
