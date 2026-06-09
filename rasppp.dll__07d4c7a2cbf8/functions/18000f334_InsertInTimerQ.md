# InsertInTimerQ

- ea: `0x18000f334`
- end: `0x18000f51f`
- name: `InsertInTimerQ`
- size: `491`
- prototype: ``
- caller_count: `13`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800023a8`
- `0x180004388`
- `0x18000b310`
- `0x18000cb10`
- `0x18000d284`
- `0x18000df18`
- `0x18000fe04`
- `0x1800126b8`
- `0x180013bb4`
- `0x180014058`
- `0x180015ae0`
- `0x1800174e0`
- `0x180017990`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180003110`
- `0x18000f334`
- `0x18002a138`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f379`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f379`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f3c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f3c2`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000f495`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000f495`

## string_xrefs

- `0x18000f3ef`: `InsertInTimerQ called portid=%d,Id=%d,Protocol=%x,EventType=%d,fAuth=%d,Timeout=%d`

## pseudocode

```c
DWORD __fastcall InsertInTimerQ(unsigned int a1, __int64 a2, unsigned int a3, int a4, int a5, int a6, int a7)
{
  _DWORD *v11; // rbx
  unsigned int v13; // edi
  _DWORD *v14; // rcx
  _QWORD *v15; // rdx
  int v16; // [rsp+50h] [rbp-848h] BYREF
  _BYTE v17[2044]; // [rsp+54h] [rbp-844h] BYREF

  v11 = HeapAlloc(hHeap, 8u, 0x30u);
  v16 = 0;
  memset_0(v17, 0, sizeof(v17));
  if ( v11 )
  {
    v13 = a7;
    if ( (byte_18004CF34 & 1) != 0 )
    {
      LOWORD(v16) = 0;
      FormatRRASErrorString(
        &v16,
        L"InsertInTimerQ called portid=%d,Id=%d,Protocol=%x,EventType=%d,fAuth=%d,Timeout=%d",
        a1,
        a3,
        a4,
        a6,
        a5,
        a7);
      if ( (byte_18004CF34 & 1) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v16);
    }
    v11[5] = a1;
    v11[9] = a3;
    v11[8] = a4;
    *((_QWORD *)v11 + 3) = a2;
    v11[4] = a6;
    v11[10] = a5;
    v14 = TimerQ;
    v15 = TimerQ;
    if ( TimerQ )
    {
      do
      {
        if ( v14[11] >= v13 )
          break;
        v13 -= v14[11];
        v15 = v14;
        v14 = *(_DWORD **)v14;
      }
      while ( v14 );
    }
    if ( v14 )
    {
      if ( v14 == TimerQ )
      {
        *(_QWORD *)v11 = TimerQ;
        *((_QWORD *)TimerQ + 1) = v11;
        *((_DWORD *)TimerQ + 11) -= v13;
        *((_QWORD *)v11 + 1) = 0;
        TimerQ = v11;
      }
      else
      {
        *(_QWORD *)v11 = *v15;
        *v15 = v11;
        *((_QWORD *)v11 + 1) = v15;
        v14[11] -= v13;
        *((_QWORD *)v14 + 1) = v11;
      }
    }
    else if ( TimerQ )
    {
      *v15 = v11;
      *((_QWORD *)v11 + 1) = v15;
      *(_QWORD *)v11 = 0;
    }
    else
    {
      TimerQ = v11;
      *(_QWORD *)v11 = 0;
      *((_QWORD *)v11 + 1) = 0;
      SetEvent(*(&TimerQ + 1));
    }
    v11[11] = v13;
    return 0;
  }
  else
  {
    if ( byte_18004CF33 < 0 )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasPppTraceError,
        L"InsertInTimerQ failed: out of memory");
    return GetLastError();
  }
}

```

## disassembly

```asm
0x18000f334  mov     [rsp+arg_8], rbx
0x18000f339  push    rbp
0x18000f33a  push    rsi
0x18000f33b  push    rdi
0x18000f33c  push    r12
0x18000f33e  push    r13
0x18000f340  push    r14
0x18000f342  push    r15
0x18000f344  sub     rsp, 860h
0x18000f34b  mov     rax, cs:__security_cookie
0x18000f352  xor     rax, rsp
0x18000f355  mov     [rsp+898h+var_48], rax
0x18000f35d  mov     r13, rdx
0x18000f360  mov     r15d, r8d
0x18000f363  mov     edx, 8; dwFlags
0x18000f368  mov     r14d, ecx
0x18000f36b  mov     rcx, cs:hHeap; hHeap
0x18000f372  mov     r12d, r9d
0x18000f375  lea     r8d, [rdx+28h]; dwBytes
0x18000f379  call    cs:__imp_HeapAlloc
0x18000f37f  xor     edx, edx; Val
0x18000f381  lea     rcx, [rsp+898h+var_844]; void *
0x18000f386  mov     rbx, rax
0x18000f389  mov     r8d, 7FCh; Size
0x18000f38f  xor     eax, eax
0x18000f391  mov     [rsp+898h+var_848], eax
0x18000f395  call    memset_0
0x18000f39a  test    rbx, rbx
0x18000f39d  jnz     short loc_18000F3CD
0x18000f39f  test    cs:byte_18004CF33, 80h
0x18000f3a6  jz      short loc_18000F3C2
0x18000f3a8  lea     r8, aInsertintimerq_1; "InsertInTimerQ failed: out of memory"
0x18000f3af  lea     rdx, RasPppTraceError
0x18000f3b6  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000f3bd  call    McTemplateU0z_EventWriteTransfer
0x18000f3c2  call    cs:__imp_GetLastError
0x18000f3c8  jmp     loc_18000F4F4
0x18000f3cd  test    cs:byte_18004CF34, 1
0x18000f3d4  mov     edi, [rsp+898h+arg_30]
0x18000f3db  mov     esi, [rsp+898h+arg_28]
0x18000f3e2  mov     ebp, [rsp+898h+arg_20]
0x18000f3e9  jz      short loc_18000F43B
0x18000f3eb  mov     [rsp+898h+var_860], edi
0x18000f3ef  lea     rdx, aInsertintimerq_0; "InsertInTimerQ called portid=%d,Id=%d,P"...
0x18000f3f6  mov     [rsp+898h+var_868], ebp
0x18000f3fa  lea     rcx, [rsp+898h+var_848]
0x18000f3ff  xor     eax, eax
0x18000f401  mov     [rsp+898h+var_870], esi
0x18000f405  mov     r9d, r15d
0x18000f408  mov     [rsp+898h+var_878], r12d
0x18000f40d  mov     r8d, r14d
0x18000f410  mov     word ptr [rsp+898h+var_848], ax
0x18000f415  call    FormatRRASErrorString
0x18000f41a  test    cs:byte_18004CF34, 1
0x18000f421  jz      short loc_18000F43B
0x18000f423  lea     r8, [rsp+898h+var_848]
0x18000f428  lea     rdx, RasPppTraceInfo
0x18000f42f  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000f436  call    McTemplateU0z_EventWriteTransfer
0x18000f43b  mov     [rbx+14h], r14d
0x18000f43f  mov     [rbx+24h], r15d
0x18000f443  mov     [rbx+20h], r12d
0x18000f447  mov     [rbx+18h], r13
0x18000f44b  mov     [rbx+10h], esi
0x18000f44e  mov     [rbx+28h], ebp
0x18000f451  mov     rax, qword ptr cs:TimerQ
0x18000f458  mov     rcx, rax
0x18000f45b  mov     rdx, rax
0x18000f45e  test    rax, rax
0x18000f461  jz      short loc_18000F476
0x18000f463  cmp     [rcx+2Ch], edi
0x18000f466  jnb     short loc_18000F476
0x18000f468  sub     edi, [rcx+2Ch]
0x18000f46b  mov     rdx, rcx
0x18000f46e  mov     rcx, [rcx]
0x18000f471  test    rcx, rcx
0x18000f474  jnz     short loc_18000F463
0x18000f476  test    rcx, rcx
0x18000f479  jnz     short loc_18000F4AD
0x18000f47b  test    rax, rax
0x18000f47e  jnz     short loc_18000F49D
0x18000f480  mov     qword ptr cs:TimerQ, rbx
0x18000f487  mov     [rbx], rax
0x18000f48a  mov     [rbx+8], rax
0x18000f48e  mov     rcx, qword ptr cs:TimerQ+8; hEvent
0x18000f495  call    cs:__imp_SetEvent
0x18000f49b  jmp     short loc_18000F4EF
0x18000f49d  mov     [rdx], rbx
0x18000f4a0  mov     [rbx+8], rdx
0x18000f4a4  mov     qword ptr [rbx], 0
0x18000f4ab  jmp     short loc_18000F4EF
0x18000f4ad  cmp     rcx, rax
0x18000f4b0  jnz     short loc_18000F4DB
0x18000f4b2  mov     [rbx], rax
0x18000f4b5  mov     rax, qword ptr cs:TimerQ
0x18000f4bc  mov     [rax+8], rbx
0x18000f4c0  mov     rax, qword ptr cs:TimerQ
0x18000f4c7  sub     [rax+2Ch], edi
0x18000f4ca  mov     qword ptr [rbx+8], 0
0x18000f4d2  mov     qword ptr cs:TimerQ, rbx
0x18000f4d9  jmp     short loc_18000F4EF
0x18000f4db  mov     rax, [rdx]
0x18000f4de  mov     [rbx], rax
0x18000f4e1  mov     [rdx], rbx
0x18000f4e4  mov     [rbx+8], rdx
0x18000f4e8  sub     [rcx+2Ch], edi
0x18000f4eb  mov     [rcx+8], rbx
0x18000f4ef  mov     [rbx+2Ch], edi
0x18000f4f2  xor     eax, eax
0x18000f4f4  mov     rcx, [rsp+898h+var_48]
0x18000f4fc  xor     rcx, rsp; StackCookie
0x18000f4ff  call    __security_check_cookie
0x18000f504  mov     rbx, [rsp+898h+arg_8]
0x18000f50c  add     rsp, 860h
0x18000f513  pop     r15
0x18000f515  pop     r14
0x18000f517  pop     r13
0x18000f519  pop     r12
0x18000f51b  pop     rdi
0x18000f51c  pop     rsi
0x18000f51d  pop     rbp
0x18000f51e  retn
```
