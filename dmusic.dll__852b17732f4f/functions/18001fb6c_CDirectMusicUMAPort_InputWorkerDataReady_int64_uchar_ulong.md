# CDirectMusicUMAPort::InputWorkerDataReady(__int64,uchar *,ulong)

- ea: `0x18001fb6c`
- end: `0x18001fdd1`
- name: `?InputWorkerDataReady@CDirectMusicUMAPort@@AEAAX_JPEAEK@Z`
- size: `613`
- prototype: `void(CDirectMusicUMAPort *__hidden this, __int64, unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18001daa8`

## callees

- `0x1800012d0`
- `0x18001ced8`
- `0x18001fb6c`
- `0x180020d6c`
- `0x1800217bc`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001fdae`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001fdae`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001fbce`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001fbce`

## pseudocode

```c
void __fastcall CDirectMusicUMAPort::InputWorkerDataReady(
        struct _RTL_CRITICAL_SECTION *this,
        __int64 a2,
        unsigned __int8 *a3,
        unsigned int a4)
{
  __int64 v8; // rax
  unsigned __int8 *v9; // r12
  __int64 v10; // rax
  _QWORD *v11; // rdi
  _QWORD *OwningThread; // rax
  int v13; // esi
  unsigned int v14; // ecx
  __int64 v15; // r12
  __int64 v16; // rax
  __int64 v17; // rsi
  _DWORD *v18; // rcx
  void *v19; // [rsp+20h] [rbp-48h] BYREF
  unsigned int Size; // [rsp+70h] [rbp+8h]
  unsigned int v21; // [rsp+88h] [rbp+20h] BYREF

  CDirectMusicUMAPort::SyncClocks((CDirectMusicUMAPort *)this);
  if ( LOBYTE(this[889].OwningThread) )
    a2 += (__int64)this[889].LockSemaphore;
  if ( a4 )
  {
    while ( a4 )
    {
      v8 = (*(_DWORD *)a3 + 27) & 0xFFFFFFF8;
      if ( (unsigned int)v8 <= a4 )
      {
        v9 = a3;
        a3 += v8;
        a4 -= v8;
        EnterCriticalSection(this + 39);
        v10 = *(unsigned int *)v9;
        if ( (unsigned int)v10 > 4 )
        {
          v13 = (v10 + 27) & 0xFFFFFFF8;
          v11 = operator new[](((v10 + 27) & 0xFFFFFFFFFFFFFFF8uLL) + 8);
        }
        else
        {
          if ( this[38].OwningThread || (unsigned __int8)CPool<QUEUED_EVENT>::RefillFreeList(&this[37].SpinCount) )
          {
            OwningThread = this[38].OwningThread;
            v11 = 0;
            if ( OwningThread )
            {
              --this[38].LockCount;
              v11 = OwningThread;
              this[38].OwningThread = (HANDLE)*OwningThread;
            }
          }
          else
          {
            v11 = 0;
          }
          v13 = 24;
        }
        if ( v11 )
        {
          memcpy_0(v11 + 1, v9, v13);
          v11[2] += a2;
          v14 = *((_DWORD *)v11 + 2);
          v19 = 0;
          v21 = 0;
          Size = (v14 + 27) & 0xFFFFFFF8;
          if ( v14 <= 3 && (*((_BYTE *)v11 + 28) & 0xF0) != 0xF0 )
          {
            v15 = *(_QWORD *)&this[889].LockCount;
            v16 = *((_BYTE *)v11 + 28) & 0xF;
            v17 = 3 * v16;
            if ( *(_QWORD *)(v15 + 24 * v16 + 8) )
            {
              if ( !*(_DWORD *)(v15 + 24 * v16 + 16)
                && (*(int (__fastcall **)(PRTL_CRITICAL_SECTION_DEBUG, void **))(*(_QWORD *)this[889].DebugInfo + 72LL))(
                     this[889].DebugInfo,
                     &v19) >= 0
                && (*(int (__fastcall **)(PRTL_CRITICAL_SECTION_DEBUG, unsigned int *))(*(_QWORD *)this[889].DebugInfo
                                                                                      + 96LL))(
                     this[889].DebugInfo,
                     &v21) >= 0
                && Size <= v21 )
              {
                if ( (*(int (__fastcall **)(PRTL_CRITICAL_SECTION_DEBUG, _QWORD))(*(_QWORD *)this[889].DebugInfo + 112LL))(
                       this[889].DebugInfo,
                       v11[2]) >= 0 )
                  (*(void (__fastcall **)(PRTL_CRITICAL_SECTION_DEBUG, _QWORD))(*(_QWORD *)this[889].DebugInfo + 120LL))(
                    this[889].DebugInfo,
                    Size);
                memcpy_0(v19, v11 + 1, Size);
                v18 = v19;
                *((_QWORD *)v19 + 1) = 50000;
                v18[1] = *(_DWORD *)(v15 + 8 * v17 + 4);
                *((_BYTE *)v18 + 20) = *(_BYTE *)(v15 + 8 * v17) | v18[5] & 0xF0;
                (*(void (__fastcall **)(_QWORD, PRTL_CRITICAL_SECTION_DEBUG))(**(_QWORD **)(v15 + 8 * v17 + 8) + 24LL))(
                  *(_QWORD *)(v15 + 8 * v17 + 8),
                  this[889].DebugInfo);
              }
            }
          }
          if ( this[38].LockSemaphore )
            *(_QWORD *)this[38].SpinCount = v11;
          else
            this[38].LockSemaphore = v11;
          this[38].SpinCount = (ULONG_PTR)v11;
          *v11 = 0;
        }
        LeaveCriticalSection(this + 39);
      }
    }
  }
}

```

## disassembly

```asm
0x18001fb6c  mov     [rsp+arg_8], rbx
0x18001fb71  push    rbp
0x18001fb72  push    rsi
0x18001fb73  push    rdi
0x18001fb74  push    r12
0x18001fb76  push    r13
0x18001fb78  push    r14
0x18001fb7a  push    r15
0x18001fb7c  sub     rsp, 30h
0x18001fb80  mov     ebp, r9d
0x18001fb83  mov     r15, r8
0x18001fb86  mov     r13, rdx
0x18001fb89  mov     rbx, rcx
0x18001fb8c  call    ?SyncClocks@CDirectMusicUMAPort@@AEAAXXZ; CDirectMusicUMAPort::SyncClocks(void)
0x18001fb91  cmp     byte ptr [rbx+8AF8h], 0
0x18001fb98  jz      short loc_18001FBA1
0x18001fb9a  add     r13, [rbx+8B00h]
0x18001fba1  test    ebp, ebp
0x18001fba3  jz      loc_18001FDBC
0x18001fba9  jmp     loc_18001FDB4
0x18001fbae  mov     eax, [r15]
0x18001fbb1  add     eax, 1Bh
0x18001fbb4  and     eax, 0FFFFFFF8h
0x18001fbb7  cmp     eax, ebp
0x18001fbb9  ja      loc_18001FDB4
0x18001fbbf  mov     r12, r15
0x18001fbc2  lea     rcx, [rbx+618h]; lpCriticalSection
0x18001fbc9  add     r15, rax
0x18001fbcc  sub     ebp, eax
0x18001fbce  call    cs:__imp_EnterCriticalSection
0x18001fbd4  mov     eax, [r12]
0x18001fbd8  cmp     eax, 4
0x18001fbdb  ja      short loc_18001FC1A
0x18001fbdd  lea     rsi, [rbx+5E8h]
0x18001fbe4  cmp     qword ptr [rsi+18h], 0
0x18001fbe9  jnz     short loc_18001FBFB
0x18001fbeb  mov     rcx, rsi
0x18001fbee  call    ?RefillFreeList@?$CPool@UQUEUED_EVENT@@@@AEAA_NXZ; CPool<QUEUED_EVENT>::RefillFreeList(void)
0x18001fbf3  test    al, al
0x18001fbf5  jnz     short loc_18001FBFB
0x18001fbf7  xor     edi, edi
0x18001fbf9  jmp     short loc_18001FC13
0x18001fbfb  mov     rax, [rsi+18h]
0x18001fbff  xor     edi, edi
0x18001fc01  test    rax, rax
0x18001fc04  jz      short loc_18001FC13
0x18001fc06  dec     dword ptr [rsi+10h]
0x18001fc09  mov     rdi, rax
0x18001fc0c  mov     rax, [rax]
0x18001fc0f  mov     [rsi+18h], rax
0x18001fc13  mov     esi, 18h
0x18001fc18  jmp     short loc_18001FC34
0x18001fc1a  lea     rcx, [rax+1Bh]
0x18001fc1e  and     rcx, 0FFFFFFFFFFFFFFF8h
0x18001fc22  lea     esi, [rax+1Bh]
0x18001fc25  add     rcx, 8; unsigned __int64
0x18001fc29  and     esi, 0FFFFFFF8h
0x18001fc2c  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001fc31  mov     rdi, rax
0x18001fc34  test    rdi, rdi
0x18001fc37  jz      loc_18001FDA7
0x18001fc3d  lea     r14, [rdi+8]
0x18001fc41  movsxd  r8, esi; Size
0x18001fc44  mov     rcx, r14; void *
0x18001fc47  mov     rdx, r12; Src
0x18001fc4a  call    memcpy_0
0x18001fc4f  add     [rdi+10h], r13
0x18001fc53  xor     edx, edx
0x18001fc55  mov     ecx, [r14]
0x18001fc58  mov     [rsp+68h+var_48], rdx
0x18001fc5d  mov     [rsp+68h+arg_18], edx
0x18001fc64  lea     eax, [rcx+1Bh]
0x18001fc67  and     eax, 0FFFFFFF8h
0x18001fc6a  mov     dword ptr [rsp+68h+Size], eax
0x18001fc6e  cmp     ecx, 3
0x18001fc71  ja      loc_18001FD7C
0x18001fc77  mov     al, [r14+14h]
0x18001fc7b  and     al, 0F0h
0x18001fc7d  cmp     al, 0F0h
0x18001fc7f  jz      loc_18001FD7C
0x18001fc85  movzx   eax, byte ptr [r14+14h]
0x18001fc8a  mov     r12, [rbx+8AF0h]
0x18001fc91  and     eax, 0Fh
0x18001fc94  lea     rsi, [rax+rax*2]
0x18001fc98  cmp     [r12+rsi*8+8], rdx
0x18001fc9d  jz      loc_18001FD7C
0x18001fca3  cmp     [r12+rsi*8+10h], edx
0x18001fca8  jnz     loc_18001FD7C
0x18001fcae  mov     rcx, [rbx+8AE8h]
0x18001fcb5  lea     rdx, [rsp+68h+var_48]
0x18001fcba  mov     rax, [rcx]
0x18001fcbd  mov     rax, [rax+48h]
0x18001fcc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fcc6  test    eax, eax
0x18001fcc8  js      loc_18001FD7C
0x18001fcce  mov     rcx, [rbx+8AE8h]
0x18001fcd5  lea     rdx, [rsp+68h+arg_18]
0x18001fcdd  mov     rax, [rcx]
0x18001fce0  mov     rax, [rax+60h]
0x18001fce4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fce9  test    eax, eax
0x18001fceb  js      loc_18001FD7C
0x18001fcf1  mov     rax, [rsp+68h+Size]
0x18001fcf6  cmp     eax, [rsp+68h+arg_18]
0x18001fcfd  ja      short loc_18001FD7C
0x18001fcff  mov     rcx, [rbx+8AE8h]
0x18001fd06  mov     rdx, [r14+8]
0x18001fd0a  mov     rax, [rcx]
0x18001fd0d  mov     rax, [rax+70h]
0x18001fd11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fd16  test    eax, eax
0x18001fd18  js      short loc_18001FD31
0x18001fd1a  mov     rcx, [rbx+8AE8h]
0x18001fd21  mov     edx, dword ptr [rsp+68h+Size]
0x18001fd25  mov     rax, [rcx]
0x18001fd28  mov     rax, [rax+78h]
0x18001fd2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fd31  mov     r8d, dword ptr [rsp+68h+Size]; Size
0x18001fd36  mov     rdx, r14; Src
0x18001fd39  mov     rcx, [rsp+68h+var_48]; void *
0x18001fd3e  call    memcpy_0
0x18001fd43  mov     rcx, [rsp+68h+var_48]
0x18001fd48  mov     qword ptr [rcx+8], 0C350h
0x18001fd50  mov     eax, [r12+rsi*8+4]
0x18001fd55  mov     [rcx+4], eax
0x18001fd58  mov     al, [rcx+14h]
0x18001fd5b  and     al, 0F0h
0x18001fd5d  or      al, [r12+rsi*8]
0x18001fd61  mov     [rcx+14h], al
0x18001fd64  mov     rcx, [r12+rsi*8+8]
0x18001fd69  mov     rdx, [rbx+8AE8h]
0x18001fd70  mov     rax, [rcx]
0x18001fd73  mov     rax, [rax+18h]
0x18001fd77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fd7c  cmp     qword ptr [rbx+608h], 0
0x18001fd84  jz      short loc_18001FD92
0x18001fd86  mov     rax, [rbx+610h]
0x18001fd8d  mov     [rax], rdi
0x18001fd90  jmp     short loc_18001FD99
0x18001fd92  mov     [rbx+608h], rdi
0x18001fd99  mov     [rbx+610h], rdi
0x18001fda0  mov     qword ptr [rdi], 0
0x18001fda7  lea     rcx, [rbx+618h]; lpCriticalSection
0x18001fdae  call    cs:__imp_LeaveCriticalSection
0x18001fdb4  test    ebp, ebp
0x18001fdb6  jnz     loc_18001FBAE
0x18001fdbc  mov     rbx, [rsp+68h+arg_8]
0x18001fdc1  add     rsp, 30h
0x18001fdc5  pop     r15
0x18001fdc7  pop     r14
0x18001fdc9  pop     r13
0x18001fdcb  pop     r12
0x18001fdcd  pop     rdi
0x18001fdce  pop     rsi
0x18001fdcf  pop     rbp
0x18001fdd0  retn
```
