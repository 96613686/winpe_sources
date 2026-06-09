# ThreadpoolManager::QueueThreadpoolWork(ThreadpoolManager::ThreadpoolType,void (*)(void *),void *)

- ea: `0x1400147f0`
- end: `0x1400148c7`
- name: `?QueueThreadpoolWork@ThreadpoolManager@@QEAAJW4ThreadpoolType@1@P6AXPEAX@Z1@Z`
- size: `215`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1400128d4`
- `0x140013350`

## callees

- `0x140001c34`
- `0x140008504`
- `0x1400147f0`
- `0x140015294`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1400148a4`
- `msvcrt!??3@YAXPEAX@Z` at `0x1400148a4`

## string_xrefs

- `0x14001488f`: `onecoreuap\admin\dm\omadm\omadmprc\threadpoolmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ThreadpoolManager::QueueThreadpoolWork(AutoThreadpool **a1, int a2, __int64 a3, __int64 a4)
{
  void (*v7)(void *); // rdx
  _QWORD *v8; // rsi
  int v9; // edi
  int v10; // edi
  unsigned int v11; // ebx
  __int64 v12; // r9
  __int64 v13; // rdx
  int v14; // eax
  int v16; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v8 = operator new(0x10u);
  *v8 = TriggerSessionWorkCallback;
  v8[1] = a4;
  v9 = a2 - 1;
  if ( v9 )
  {
    v10 = v9 - 1;
    if ( v10 )
    {
      if ( v10 != 1 )
      {
        v11 = -2147418113;
        v12 = 2147549183LL;
        v13 = 80;
LABEL_12:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v13,
          (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmprc\\threadpoolmanager.cpp",
          (const char *)v12,
          v16);
        operator delete(v8);
        return v11;
      }
      v14 = AutoThreadpool::QueueThreadpoolWork(a1[2], v7, v8);
      v11 = v14;
      if ( v14 < 0 )
      {
        v13 = 77;
LABEL_11:
        v12 = (unsigned int)v14;
        goto LABEL_12;
      }
    }
    else
    {
      v14 = AutoThreadpool::QueueThreadpoolWork(a1[1], v7, v8);
      v11 = v14;
      if ( v14 < 0 )
      {
        v13 = 74;
        goto LABEL_11;
      }
    }
  }
  else
  {
    v14 = AutoThreadpool::QueueThreadpoolWork(a1[3], v7, v8);
    v11 = v14;
    if ( v14 < 0 )
    {
      v13 = 71;
      goto LABEL_11;
    }
  }
  _InterlockedIncrement(&ThreadpoolManager::m_numberOfWorkQueued);
  return 0;
}

```

## disassembly

```asm
0x1400147f0  mov     [rsp+arg_10], r8
0x1400147f5  push    rbx
0x1400147f6  push    rbp
0x1400147f7  push    rsi
0x1400147f8  push    rdi
0x1400147f9  sub     rsp, 28h
0x1400147fd  mov     rbx, r9
0x140014800  mov     edi, edx
0x140014802  mov     rbp, rcx
0x140014805  mov     ecx, 10h; Size
0x14001480a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14001480f  mov     rsi, rax
0x140014812  mov     [rsp+48h+arg_10], rax
0x140014817  lea     rax, ?TriggerSessionWorkCallback@@YAXPEAX@Z; TriggerSessionWorkCallback(void *)
0x14001481e  mov     [rsi], rax
0x140014821  mov     [rsi+8], rbx
0x140014825  sub     edi, 1
0x140014828  jz      short loc_140014875
0x14001482a  sub     edi, 1
0x14001482d  jz      short loc_14001485C
0x14001482f  cmp     edi, 1
0x140014832  jz      short loc_140014843
0x140014834  mov     ebx, 8000FFFFh
0x140014839  mov     r9d, ebx
0x14001483c  mov     edx, 50h ; 'P'
0x140014841  jmp     short loc_14001488F
0x140014843  mov     r8, rsi; void *
0x140014846  mov     rcx, [rbp+10h]; this
0x14001484a  call    ?QueueThreadpoolWork@AutoThreadpool@@QEAAJP6AXPEAX@Z0@Z; AutoThreadpool::QueueThreadpoolWork(void (*)(void *),void *)
0x14001484f  mov     ebx, eax
0x140014851  test    eax, eax
0x140014853  jns     short loc_1400148B4
0x140014855  mov     edx, 4Dh ; 'M'
0x14001485a  jmp     short loc_14001488C
0x14001485c  mov     r8, rsi; void *
0x14001485f  mov     rcx, [rbp+8]; this
0x140014863  call    ?QueueThreadpoolWork@AutoThreadpool@@QEAAJP6AXPEAX@Z0@Z; AutoThreadpool::QueueThreadpoolWork(void (*)(void *),void *)
0x140014868  mov     ebx, eax
0x14001486a  test    eax, eax
0x14001486c  jns     short loc_1400148B4
0x14001486e  mov     edx, 4Ah ; 'J'
0x140014873  jmp     short loc_14001488C
0x140014875  mov     r8, rsi; void *
0x140014878  mov     rcx, [rbp+18h]; this
0x14001487c  call    ?QueueThreadpoolWork@AutoThreadpool@@QEAAJP6AXPEAX@Z0@Z; AutoThreadpool::QueueThreadpoolWork(void (*)(void *),void *)
0x140014881  mov     ebx, eax
0x140014883  test    eax, eax
0x140014885  jns     short loc_1400148B4
0x140014887  mov     edx, 47h ; 'G'; void *
0x14001488c  mov     r9d, eax; char *
0x14001488f  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\dm\\omadm\\omadmprc"...
0x140014896  mov     rcx, [rsp+48h]; this
0x14001489b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400148a0  nop
0x1400148a1  mov     rcx, rsi
0x1400148a4  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1400148ab  nop     dword ptr [rax+rax+00h]
0x1400148b0  mov     eax, ebx
0x1400148b2  jmp     short loc_1400148BD
0x1400148b4  lock inc cs:?m_numberOfWorkQueued@ThreadpoolManager@@0JC; long volatile ThreadpoolManager::m_numberOfWorkQueued
0x1400148bb  xor     eax, eax
0x1400148bd  add     rsp, 28h
0x1400148c1  pop     rdi
0x1400148c2  pop     rsi
0x1400148c3  pop     rbp
0x1400148c4  pop     rbx
0x1400148c5  retn
```
