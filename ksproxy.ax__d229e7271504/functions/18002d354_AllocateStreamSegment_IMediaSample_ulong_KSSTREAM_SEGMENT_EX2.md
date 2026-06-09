# AllocateStreamSegment(IMediaSample *,ulong,_KSSTREAM_SEGMENT_EX2 * *)

- ea: `0x18002d354`
- end: `0x18002d4d2`
- name: `?AllocateStreamSegment@@YAJPEAUIMediaSample@@KPEAPEAU_KSSTREAM_SEGMENT_EX2@@@Z`
- size: `382`
- prototype: `__int64 __fastcall(struct IMediaSample *, int, struct _KSSTREAM_SEGMENT_EX2 **)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18002e2dc`
- `0x18002f494`

## callees

- `0x18000e210`
- `0x18001f1c4`
- `0x18001f1d0`
- `0x18001f210`
- `0x18001ffb0`
- `0x18002d354`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x18002d3ca`
- `KERNEL32!CreateEventW` at `0x18002d3ca`
- `KERNEL32!CloseHandle` at `0x18002d442`
- `KERNEL32!CloseHandle` at `0x18002d442`

## pseudocode

```c
__int64 __fastcall AllocateStreamSegment(struct IMediaSample *a1, int a2, struct _KSSTREAM_SEGMENT_EX2 **a3)
{
  void *v6; // rdi
  int SampleProperties; // esi
  _DWORD *v8; // rbx
  HANDLE EventW; // rbp
  unsigned __int64 v10; // rdx
  unsigned __int64 v11; // rdx
  struct tagAM_SAMPLE2_PROPERTIES v13; // [rsp+20h] [rbp-88h] BYREF

  memset_0(&v13, 0, sizeof(v13));
  v6 = operator new(0x258u);
  if ( !v6 )
    return (unsigned int)-2147024882;
  v8 = operator new[]((unsigned int)(a2 + 56));
  if ( !v8 )
  {
    operator delete(v6, 0x258u);
    return (unsigned int)-2147024882;
  }
  EventW = CreateEventW(0, 0, 0, 0);
  if ( EventW )
  {
    memset_0(v6, 0, 0x258u);
    memset_0(v8, 0, (unsigned int)(a2 + 56));
    SampleProperties = GetSampleProperties(a1, &v13);
    if ( SampleProperties >= 0 )
    {
      *v8 = a2 + 56;
      v8[12] = v13.dwSampleFlags;
      v8[1] = v13.dwTypeSpecificFlags;
      *((_QWORD *)v8 + 1) = v13.tStart;
      v8[4] = 1;
      v8[5] = 1;
      *((_QWORD *)v8 + 3) = v13.tStop - v13.tStart;
      *((_QWORD *)v8 + 5) = v13.pbBuffer;
      v8[8] = v13.cbBuffer;
      *((_QWORD *)v6 + 69) = v8;
      *((_DWORD *)v6 + 137) = a2;
      *((_QWORD *)v6 + 4) = a1;
      *((_DWORD *)v6 + 136) = 0;
      *((_QWORD *)v6 + 73) = EventW;
      *((_QWORD *)v6 + 3) = EventW;
      *a3 = (struct _KSSTREAM_SEGMENT_EX2 *)v6;
    }
    else
    {
      operator delete(v6, 0x258u);
      operator delete(v8, v11);
      CloseHandle(EventW);
    }
  }
  else
  {
    operator delete(v6, 0x258u);
    operator delete(v8, v10);
    return (unsigned int)-2147467259;
  }
  return (unsigned int)SampleProperties;
}

```

## disassembly

```asm
0x18002d354  push    rbx
0x18002d356  push    rbp
0x18002d357  push    rsi
0x18002d358  push    rdi
0x18002d359  push    r12
0x18002d35b  push    r13
0x18002d35d  push    r14
0x18002d35f  push    r15
0x18002d361  sub     rsp, 68h
0x18002d365  mov     r15d, edx
0x18002d368  mov     r13, r8
0x18002d36b  xor     edx, edx; Val
0x18002d36d  mov     r12, rcx
0x18002d370  lea     rcx, [rsp+0A8h+var_88]; void *
0x18002d375  lea     r8d, [rdx+40h]; Size
0x18002d379  call    memset_0
0x18002d37e  mov     ebp, 258h
0x18002d383  mov     ecx, ebp; Size
0x18002d385  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002d38a  mov     rdi, rax
0x18002d38d  test    rax, rax
0x18002d390  jnz     short loc_18002D39C
0x18002d392  mov     esi, 8007000Eh
0x18002d397  jmp     loc_18002D4BE
0x18002d39c  lea     r14d, [r15+38h]
0x18002d3a0  mov     ecx, r14d; unsigned __int64
0x18002d3a3  mov     esi, r14d
0x18002d3a6  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18002d3ab  mov     rbx, rax
0x18002d3ae  test    rax, rax
0x18002d3b1  jnz     short loc_18002D3C0
0x18002d3b3  mov     rdx, rbp; unsigned __int64
0x18002d3b6  mov     rcx, rdi; void *
0x18002d3b9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002d3be  jmp     short loc_18002D392
0x18002d3c0  xor     r9d, r9d; lpName
0x18002d3c3  xor     r8d, r8d; bInitialState
0x18002d3c6  xor     edx, edx; bManualReset
0x18002d3c8  xor     ecx, ecx; lpEventAttributes
0x18002d3ca  call    cs:__imp_CreateEventW
0x18002d3d1  nop     dword ptr [rax+rax+00h]
0x18002d3d6  mov     rbp, rax
0x18002d3d9  mov     rcx, rdi; void *
0x18002d3dc  test    rax, rax
0x18002d3df  jnz     short loc_18002D3FD
0x18002d3e1  mov     edx, 258h; unsigned __int64
0x18002d3e6  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002d3eb  mov     rcx, rbx; void *
0x18002d3ee  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002d3f3  mov     esi, 80004005h
0x18002d3f8  jmp     loc_18002D4BE
0x18002d3fd  xor     edx, edx; Val
0x18002d3ff  mov     r8d, 258h; Size
0x18002d405  call    memset_0
0x18002d40a  mov     r8, rsi; Size
0x18002d40d  xor     edx, edx; Val
0x18002d40f  mov     rcx, rbx; void *
0x18002d412  call    memset_0
0x18002d417  lea     rdx, [rsp+0A8h+var_88]; struct tagAM_SAMPLE2_PROPERTIES *
0x18002d41c  mov     rcx, r12; struct IMediaSample *
0x18002d41f  call    ?GetSampleProperties@@YAJPEAUIMediaSample@@PEAUtagAM_SAMPLE2_PROPERTIES@@@Z; GetSampleProperties(IMediaSample *,tagAM_SAMPLE2_PROPERTIES *)
0x18002d424  mov     esi, eax
0x18002d426  test    eax, eax
0x18002d428  jns     short loc_18002D450
0x18002d42a  mov     edx, 258h; unsigned __int64
0x18002d42f  mov     rcx, rdi; void *
0x18002d432  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002d437  mov     rcx, rbx; void *
0x18002d43a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002d43f  mov     rcx, rbp; hObject
0x18002d442  call    cs:__imp_CloseHandle
0x18002d449  nop     dword ptr [rax+rax+00h]
0x18002d44e  jmp     short loc_18002D4BE
0x18002d450  mov     [rbx], r14d
0x18002d453  mov     eax, [rsp+0A8h+var_88.dwSampleFlags]
0x18002d457  mov     [rbx+30h], eax
0x18002d45a  mov     eax, [rsp+0A8h+var_88.dwTypeSpecificFlags]
0x18002d45e  mov     [rbx+4], eax
0x18002d461  mov     rax, [rsp+0A8h+var_88.tStart]
0x18002d466  mov     [rbx+8], rax
0x18002d46a  mov     eax, 1
0x18002d46f  mov     [rbx+10h], eax
0x18002d472  mov     [rbx+14h], eax
0x18002d475  mov     rax, [rsp+0A8h+var_88.tStop]
0x18002d47a  sub     rax, [rsp+0A8h+var_88.tStart]
0x18002d47f  mov     [rbx+18h], rax
0x18002d483  mov     rax, [rsp+0A8h+var_88.pbBuffer]
0x18002d488  mov     [rbx+28h], rax
0x18002d48c  mov     eax, [rsp+0A8h+var_88.cbBuffer]
0x18002d490  mov     [rbx+20h], eax
0x18002d493  mov     [rdi+228h], rbx
0x18002d49a  mov     [rdi+224h], r15d
0x18002d4a1  mov     [rdi+20h], r12
0x18002d4a5  mov     dword ptr [rdi+220h], 0
0x18002d4af  mov     [rdi+248h], rbp
0x18002d4b6  mov     [rdi+18h], rbp
0x18002d4ba  mov     [r13+0], rdi
0x18002d4be  mov     eax, esi
0x18002d4c0  add     rsp, 68h
0x18002d4c4  pop     r15
0x18002d4c6  pop     r14
0x18002d4c8  pop     r13
0x18002d4ca  pop     r12
0x18002d4cc  pop     rdi
0x18002d4cd  pop     rsi
0x18002d4ce  pop     rbp
0x18002d4cf  pop     rbx
0x18002d4d0  retn
```
