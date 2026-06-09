# CreateDsClock

- ea: `0x18001a840`
- end: `0x18001a96f`
- name: `CreateDsClock`
- size: `303`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops`

## callees

- `0x1800012c4`
- `0x18000a974`
- `0x18001a7d4`
- `0x18001a840`
- `0x18001aa70`
- `0x1800217b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001a859`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001a859`

## pseudocode

```c
__int64 __fastcall CreateDsClock(_QWORD *a1, CMasterClock *a2)
{
  void *v4; // rax
  volatile signed __int32 *v5; // rbx
  int DefaultMasterClock; // esi
  unsigned int v8; // edi
  __int64 v9; // rdx

  v4 = malloc(0x28u);
  v5 = (volatile signed __int32 *)v4;
  if ( v4 )
  {
    *((_DWORD *)v4 + 4) = 1;
    *(_QWORD *)v4 = &CDsClock::`vftable'{for `IReferenceClock'};
    *((_QWORD *)v4 + 1) = &CDsClock::`vftable'{for `IDirectSoundSinkSync'};
    *((_QWORD *)v4 + 3) = 0;
    *((_QWORD *)v4 + 4) = 0;
    DefaultMasterClock = CMasterClock::CreateDefaultMasterClock(a2, (struct IReferenceClock **)v4 + 3);
    if ( DefaultMasterClock < 0 )
    {
      CDsClock::~CDsClock((CDsClock *)v5);
      operator delete((void *)v5);
      return (unsigned int)DefaultMasterClock;
    }
    if ( !a1 )
    {
      v8 = -2147467261;
LABEL_13:
      CDsClock::Release((CDsClock *)v5);
      return v8;
    }
    *a1 = 0;
    if ( !memcmp_0(&IID_IReferenceClock, &IID_IUnknown, 0x10u)
      || !memcmp_0(&IID_IReferenceClock, &IID_IReferenceClock, 0x10u) )
    {
      v9 = (__int64)v5;
    }
    else
    {
      if ( memcmp_0(&IID_IReferenceClock, &IID_IDirectSoundSinkSync, 0x10u) )
      {
        v8 = -2147467262;
        goto LABEL_13;
      }
      v9 = (unsigned __int64)(v5 + 2) & ((unsigned __int128)-(__int128)(unsigned __int64)v5 >> 64);
    }
    *a1 = v9;
    _InterlockedIncrement(v5 + 4);
    v8 = 0;
    goto LABEL_13;
  }
  return 2147942414LL;
}

```

## disassembly

```asm
0x18001a840  push    rbx
0x18001a842  push    rsi
0x18001a843  push    rdi
0x18001a844  push    r14
0x18001a846  sub     rsp, 28h
0x18001a84a  mov     rdi, rcx
0x18001a84d  mov     r14d, 28h ; '('
0x18001a853  mov     ecx, r14d; Size
0x18001a856  mov     rsi, rdx
0x18001a859  call    cs:__imp_malloc
0x18001a85f  mov     [rsp+48h+arg_10], rax
0x18001a864  mov     rbx, rax
0x18001a867  test    rax, rax
0x18001a86a  jz      loc_18001A960
0x18001a870  mov     dword ptr [rbx+10h], 1
0x18001a877  lea     rax, ??_7CDsClock@@6BIReferenceClock@@@; const CDsClock::`vftable'{for `IReferenceClock'}
0x18001a87e  mov     [rbx], rax
0x18001a881  lea     rax, ??_7CDsClock@@6BIDirectSoundSinkSync@@@; const CDsClock::`vftable'{for `IDirectSoundSinkSync'}
0x18001a888  mov     [rbx+8], rax
0x18001a88c  mov     qword ptr [rbx+18h], 0
0x18001a894  mov     qword ptr [rbx+20h], 0
0x18001a89c  test    rbx, rbx
0x18001a89f  jz      loc_18001A960
0x18001a8a5  lea     rdx, [rbx+18h]; struct IReferenceClock **
0x18001a8a9  mov     rcx, rsi; this
0x18001a8ac  call    ?CreateDefaultMasterClock@CMasterClock@@QEAAJPEAPEAUIReferenceClock@@@Z; CMasterClock::CreateDefaultMasterClock(IReferenceClock * *)
0x18001a8b1  mov     esi, eax
0x18001a8b3  test    eax, eax
0x18001a8b5  jns     short loc_18001A8D1
0x18001a8b7  mov     rcx, rbx; this
0x18001a8ba  call    ??1CDsClock@@QEAA@XZ; CDsClock::~CDsClock(void)
0x18001a8bf  mov     edx, r14d; unsigned __int64
0x18001a8c2  mov     rcx, rbx; void *
0x18001a8c5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001a8ca  mov     eax, esi
0x18001a8cc  jmp     loc_18001A965
0x18001a8d1  test    rdi, rdi
0x18001a8d4  jnz     short loc_18001A8DD
0x18001a8d6  mov     edi, 80004003h
0x18001a8db  jmp     short loc_18001A954
0x18001a8dd  mov     r14d, 10h
0x18001a8e3  mov     qword ptr [rdi], 0
0x18001a8ea  lea     rsi, IID_IReferenceClock
0x18001a8f1  mov     r8d, r14d; Size
0x18001a8f4  mov     rcx, rsi; Buf1
0x18001a8f7  lea     rdx, IID_IUnknown; Buf2
0x18001a8fe  call    memcmp_0
0x18001a903  test    eax, eax
0x18001a905  jz      short loc_18001A948
0x18001a907  mov     r8d, r14d; Size
0x18001a90a  mov     rdx, rsi; Buf2
0x18001a90d  mov     rcx, rsi; Buf1
0x18001a910  call    memcmp_0
0x18001a915  test    eax, eax
0x18001a917  jz      short loc_18001A948
0x18001a919  mov     r8d, r14d; Size
0x18001a91c  lea     rdx, IID_IDirectSoundSinkSync; Buf2
0x18001a923  mov     rcx, rsi; Buf1
0x18001a926  call    memcmp_0
0x18001a92b  test    eax, eax
0x18001a92d  jnz     short loc_18001A941
0x18001a92f  mov     rax, rbx
0x18001a932  lea     rcx, [rbx+8]
0x18001a936  neg     rax
0x18001a939  sbb     rdx, rdx
0x18001a93c  and     rdx, rcx
0x18001a93f  jmp     short loc_18001A94B
0x18001a941  mov     edi, 80004002h
0x18001a946  jmp     short loc_18001A954
0x18001a948  mov     rdx, rbx
0x18001a94b  mov     [rdi], rdx
0x18001a94e  lock inc dword ptr [rbx+10h]
0x18001a952  xor     edi, edi
0x18001a954  mov     rcx, rbx; this
0x18001a957  call    ?Release@CDsClock@@UEAAKXZ; CDsClock::Release(void)
0x18001a95c  mov     eax, edi
0x18001a95e  jmp     short loc_18001A965
0x18001a960  mov     eax, 8007000Eh
0x18001a965  add     rsp, 28h
0x18001a969  pop     r14
0x18001a96b  pop     rdi
0x18001a96c  pop     rsi
0x18001a96d  pop     rbx
0x18001a96e  retn
```
