# CGhostThread::Initialize(ushort const *)

- ea: `0x180008834`
- end: `0x18000893e`
- name: `?Initialize@CGhostThread@@QEAAHPEBG@Z`
- size: `266`
- prototype: `__int64 __fastcall(CGhostThread *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180007d0c`

## callees

- `0x180008834`
- `0x180008b00`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800088ac`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800088ac`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180008851`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180008851`
- `ext-ms-win-ntuser-windowstation-l1-1-2!OpenDesktopW` at `0x18000892b`
- `ext-ms-win-ntuser-windowstation-l1-1-2!OpenDesktopW` at `0x18000892b`

## pseudocode

```c
__int64 __fastcall CGhostThread::Initialize(CGhostThread *this, const unsigned __int16 *a2)
{
  HANDLE EventW; // rax
  unsigned int v5; // edi
  __int64 v6; // rax
  const unsigned __int16 *v7; // rcx
  SIZE_T v8; // rbx
  _WORD *v9; // rax
  unsigned __int64 v10; // rbx
  __int64 v11; // rdx
  __int64 v13; // rcx
  _WORD *v14; // rcx
  HDESK v15; // rax

  EventW = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 8) = EventW;
  if ( EventW && a2 )
  {
    v5 = 1;
    v6 = 0x7FFFFFFF;
    v7 = a2;
    do
    {
      if ( !*v7 )
        break;
      ++v7;
      --v6;
    }
    while ( v6 );
    if ( v6 )
    {
      v8 = (-(__int64)(v6 != 0) & (2 * (0x7FFFFFFF - v6))) + 2;
      v9 = HeapAlloc(g_hProcessHeap, 0, v8);
      *((_QWORD *)this + 9) = v9;
      if ( v9 )
      {
        v10 = v8 >> 1;
        if ( v10 )
        {
          if ( v10 <= 0x7FFFFFFF )
          {
            v13 = 2147483646;
            do
            {
              if ( !v13 )
                break;
              if ( !*a2 )
                break;
              *v9++ = *a2++;
              --v13;
              --v10;
            }
            while ( v10 );
            v14 = v9 - 1;
            if ( v10 )
              v14 = v9;
            *v14 = 0;
            if ( v10 )
            {
              v15 = OpenDesktopW(*((LPCWSTR *)this + 9), 0, 0, 3u);
              *((_QWORD *)this + 10) = v15;
              if ( v15 )
              {
                v11 = 1;
                goto LABEL_12;
              }
            }
          }
          else
          {
            *v9 = 0;
          }
        }
      }
    }
  }
  v5 = 0;
  v11 = 4;
LABEL_12:
  CGhostThread::SetState(this, v11);
  return v5;
}

```

## disassembly

```asm
0x180008834  push    rbx
0x180008836  push    rbp
0x180008837  push    rsi
0x180008838  push    rdi
0x180008839  push    r14
0x18000883b  push    r15
0x18000883d  sub     rsp, 28h
0x180008841  mov     r14, rdx
0x180008844  mov     rsi, rcx
0x180008847  xor     edx, edx; bManualReset
0x180008849  xor     ecx, ecx; lpEventAttributes
0x18000884b  xor     r9d, r9d; lpName
0x18000884e  xor     r8d, r8d; bInitialState
0x180008851  call    cs:__imp_CreateEventW
0x180008857  xor     ebp, ebp
0x180008859  mov     [rsi+40h], rax
0x18000885d  test    rax, rax
0x180008860  jz      short loc_1800088C8
0x180008862  test    r14, r14
0x180008865  jz      short loc_1800088C8
0x180008867  mov     r15d, 7FFFFFFFh
0x18000886d  lea     edi, [rbp+1]
0x180008870  mov     eax, r15d
0x180008873  mov     rcx, r14
0x180008876  cmp     [rcx], bp
0x180008879  jz      short loc_180008884
0x18000887b  add     rcx, 2
0x18000887f  sub     rax, rdi
0x180008882  jnz     short loc_180008876
0x180008884  test    rax, rax
0x180008887  jz      short loc_1800088C8
0x180008889  mov     rcx, r15
0x18000888c  sub     rcx, rax
0x18000888f  neg     rax
0x180008892  sbb     rax, rax
0x180008895  xor     edx, edx; dwFlags
0x180008897  lea     rbx, [rcx+rcx]
0x18000889b  mov     rcx, cs:g_hProcessHeap; hHeap
0x1800088a2  and     rbx, rax
0x1800088a5  add     rbx, 2
0x1800088a9  mov     r8, rbx; dwBytes
0x1800088ac  call    cs:__imp_HeapAlloc
0x1800088b2  mov     [rsi+48h], rax
0x1800088b6  test    rax, rax
0x1800088b9  jz      short loc_1800088C8
0x1800088bb  shr     rbx, 1
0x1800088be  jz      short loc_1800088C8
0x1800088c0  cmp     rbx, r15
0x1800088c3  jbe     short loc_1800088E6
0x1800088c5  mov     [rax], bp
0x1800088c8  mov     edi, ebp
0x1800088ca  mov     edx, 4
0x1800088cf  mov     rcx, rsi
0x1800088d2  call    ?SetState@CGhostThread@@AEAA?AW4tagGHOSTTHREADSTATE@@W42@@Z; CGhostThread::SetState(tagGHOSTTHREADSTATE)
0x1800088d7  mov     eax, edi
0x1800088d9  add     rsp, 28h
0x1800088dd  pop     r15
0x1800088df  pop     r14
0x1800088e1  pop     rdi
0x1800088e2  pop     rsi
0x1800088e3  pop     rbp
0x1800088e4  pop     rbx
0x1800088e5  retn
0x1800088e6  mov     ecx, 7FFFFFFEh
0x1800088eb  test    rcx, rcx
0x1800088ee  jz      short loc_18000890C
0x1800088f0  movzx   edx, word ptr [r14]
0x1800088f4  test    dx, dx
0x1800088f7  jz      short loc_18000890C
0x1800088f9  mov     [rax], dx
0x1800088fc  add     r14, 2
0x180008900  add     rax, 2
0x180008904  sub     rcx, rdi
0x180008907  sub     rbx, rdi
0x18000890a  jnz     short loc_1800088EB
0x18000890c  test    rbx, rbx
0x18000890f  lea     rcx, [rax-2]
0x180008913  cmovnz  rcx, rax
0x180008917  mov     [rcx], bp
0x18000891a  jz      short loc_1800088C8
0x18000891c  mov     rcx, [rsi+48h]; lpszDesktop
0x180008920  mov     r9d, 3; dwDesiredAccess
0x180008926  xor     r8d, r8d; fInherit
0x180008929  xor     edx, edx; dwFlags
0x18000892b  call    cs:__imp_OpenDesktopW
0x180008931  mov     [rsi+50h], rax
0x180008935  test    rax, rax
0x180008938  jz      short loc_1800088C8
0x18000893a  mov     edx, edi
0x18000893c  jmp     short loc_1800088CF
```
