# CompleteAppRecvsUponClose

- ea: `0x180046240`
- end: `0x1800462a9`
- name: `CompleteAppRecvsUponClose`
- size: `105`
- prototype: `__int64 __fastcall(PVOID CompletionContext)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18003b114`
- `0x180047cb0`
- `0x18004958c`
- `0x18005284c`

## callees

- `0x18003cdc8`
- `0x180046240`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180046287`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180046287`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180046255`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180046255`

## pseudocode

```c
void __fastcall CompleteAppRecvsUponClose(char *CompletionContext, __int64 a2, int a3)
{
  int v5; // ebx
  char *v6; // rax

  v5 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
  v6 = (char *)*((_QWORD *)CompletionContext + 40);
  if ( v6 != CompletionContext + 320 )
  {
    v5 = 1;
    do
    {
      *((_DWORD *)v6 + 5) = 1;
      *((_DWORD *)v6 + 4) = a3;
      v6 = *(char **)v6;
    }
    while ( v6 != CompletionContext + 320 );
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
  if ( v5 )
    CheckPendingAppRecvs(CompletionContext);
}

```

## disassembly

```asm
0x180046240  push    rbx
0x180046242  push    rbp
0x180046243  push    rsi
0x180046244  push    rdi
0x180046245  sub     rsp, 28h
0x180046249  mov     rdi, rcx
0x18004624c  mov     ebp, r8d
0x18004624f  add     rcx, 30h ; '0'; lpCriticalSection
0x180046253  xor     ebx, ebx
0x180046255  call    cs:__imp_EnterCriticalSection
0x18004625c  nop     dword ptr [rax+rax+00h]
0x180046261  lea     rdx, [rdi+140h]
0x180046268  mov     rax, [rdx]
0x18004626b  cmp     rax, rdx
0x18004626e  jz      short loc_180046283
0x180046270  mov     ebx, 1
0x180046275  mov     [rax+14h], ebx
0x180046278  mov     [rax+10h], ebp
0x18004627b  mov     rax, [rax]
0x18004627e  cmp     rax, rdx
0x180046281  jnz     short loc_180046275
0x180046283  lea     rcx, [rdi+30h]; lpCriticalSection
0x180046287  call    cs:__imp_LeaveCriticalSection
0x18004628e  nop     dword ptr [rax+rax+00h]
0x180046293  test    ebx, ebx
0x180046295  jz      short loc_18004629F
0x180046297  mov     rcx, rdi; CompletionContext
0x18004629a  call    CheckPendingAppRecvs
0x18004629f  add     rsp, 28h
0x1800462a3  pop     rdi
0x1800462a4  pop     rsi
0x1800462a5  pop     rbp
0x1800462a6  pop     rbx
0x1800462a7  retn
```
