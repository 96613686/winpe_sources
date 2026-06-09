# CSynth::SetReverbActive(int)

- ea: `0x1800073a0`
- end: `0x1800074a1`
- name: `?SetReverbActive@CSynth@@QEAAXH@Z`
- size: `257`
- prototype: `void __fastcall(CSynth *__hidden this, int)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180012090`
- `0x180012460`

## callees

- `0x180001d9a`
- `0x180001fe0`
- `0x180007340`
- `0x1800073a0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800073ee`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180007400`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800073ee`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180007400`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800073bb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800073bb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000749a`

## pseudocode

```c
void __fastcall CSynth::SetReverbActive(CSynth *this, int a2)
{
  void *v4; // rax
  bool v5; // zf
  __int64 v6; // rcx
  void *v7; // rcx

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 1048));
  if ( *((_DWORD *)this + 34) != a2 )
  {
    *((_DWORD *)this + 34) = a2;
    if ( a2 )
    {
      if ( *((_QWORD *)this + 19) )
      {
        v7 = (void *)*((_QWORD *)this + 18);
        if ( v7 )
          memset_0(v7, 0, 0x14008u);
      }
      else
      {
        *((_QWORD *)this + 19) = malloc(0x94u);
        v4 = malloc(0x14008u);
        v5 = *((_QWORD *)this + 19) == 0;
        *((_QWORD *)this + 18) = v4;
        if ( !v5 && v4 )
        {
          memset_0(v4, 0, 0x14008u);
          InitSVerb(v6, *((_QWORD *)this + 19));
          memset_0(*((void **)this + 18), 0, 0x14008u);
          CSynth::SetReverb(this, (struct _DMUS_WAVES_REVERB_PARAMS *)this + 10);
        }
      }
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 1048));
}

```

## disassembly

```asm
0x1800073a0  mov     [rsp+arg_0], rbx
0x1800073a5  mov     [rsp+arg_8], rsi
0x1800073aa  push    rdi
0x1800073ab  sub     rsp, 20h
0x1800073af  mov     rbx, rcx
0x1800073b2  mov     edi, edx
0x1800073b4  add     rcx, 418h; lpCriticalSection
0x1800073bb  call    cs:__imp_EnterCriticalSection
0x1800073c1  cmp     [rbx+88h], edi
0x1800073c7  jz      loc_180007484
0x1800073cd  mov     [rbx+88h], edi
0x1800073d3  test    edi, edi
0x1800073d5  jz      loc_180007484
0x1800073db  cmp     qword ptr [rbx+98h], 0
0x1800073e3  jnz     loc_18000746B
0x1800073e9  mov     ecx, 94h; Size
0x1800073ee  call    cs:__imp_malloc
0x1800073f4  mov     ecx, 14008h; Size
0x1800073f9  mov     [rbx+98h], rax
0x180007400  call    cs:__imp_malloc
0x180007406  cmp     qword ptr [rbx+98h], 0
0x18000740e  mov     [rbx+90h], rax
0x180007415  jz      short loc_180007484
0x180007417  test    rax, rax
0x18000741a  jz      short loc_180007484
0x18000741c  xor     edx, edx; Val
0x18000741e  mov     r8d, 14008h; Size
0x180007424  mov     rcx, rax; void *
0x180007427  call    memset_0
0x18000742c  mov     eax, [rbx+0D0h]
0x180007432  xorps   xmm0, xmm0
0x180007435  mov     rdx, [rbx+98h]
0x18000743c  cvtsi2ss xmm0, rax
0x180007441  call    InitSVerb
0x180007446  mov     rcx, [rbx+90h]; void *
0x18000744d  xor     edx, edx; Val
0x18000744f  mov     r8d, 14008h; Size
0x180007455  call    memset_0
0x18000745a  lea     rdx, [rbx+0A0h]; struct _DMUS_WAVES_REVERB_PARAMS *
0x180007461  mov     rcx, rbx; this
0x180007464  call    ?SetReverb@CSynth@@QEAAJPEAU_DMUS_WAVES_REVERB_PARAMS@@@Z; CSynth::SetReverb(_DMUS_WAVES_REVERB_PARAMS *)
0x180007469  jmp     short loc_180007484
0x18000746b  mov     rcx, [rbx+90h]; void *
0x180007472  test    rcx, rcx
0x180007475  jz      short loc_180007484
0x180007477  xor     edx, edx; Val
0x180007479  mov     r8d, 14008h; Size
0x18000747f  call    memset_0
0x180007484  lea     rcx, [rbx+418h]
0x18000748b  mov     rbx, [rsp+28h+arg_0]
0x180007490  mov     rsi, [rsp+28h+arg_8]
0x180007495  add     rsp, 20h
0x180007499  pop     rdi
0x18000749a  jmp     cs:__imp_LeaveCriticalSection
```
