# LsaDbpCreateThreadInfo(void)

- ea: `0x180015664`
- end: `0x180015719`
- name: `?LsaDbpCreateThreadInfo@@YAPEAU_LSADS_PER_THREAD_INFO@@XZ`
- size: `181`
- prototype: `struct _LSADS_PER_THREAD_INFO *(void)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800154f0`
- `0x18001fdd0`

## callees

- `0x180015664`
- `0x1800157c8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800156c5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800156c5`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800156a6`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800156a6`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180015674`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180015674`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800156bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800156bd`
- `LSASRV!LsapAllocateLsaHeap` at `0x18001568f`
- `LSASRV!LsapAllocateLsaHeap` at `0x18001568f`
- `LSASRV!LsapFreeLsaHeap` at `0x1800156ee`
- `LSASRV!LsapFreeLsaHeap` at `0x1800156ee`

## pseudocode

```c
struct _LSADS_PER_THREAD_INFO *LsaDbpCreateThreadInfo(void)
{
  _DWORD *Value; // rax
  _DWORD *v1; // rdi
  _DWORD *LsaHeap; // rax
  __int64 v3; // rdx
  __int64 v4; // r8
  DWORD LastError; // ebx
  DWORD CurrentThreadId; // eax
  __int64 v7; // r8

  Value = TlsGetValue(LsaDbpDsThreadState);
  v1 = Value;
  if ( Value )
  {
    ++Value[1];
  }
  else
  {
    LsaHeap = (_DWORD *)LsapAllocateLsaHeap(40);
    v1 = LsaHeap;
    if ( LsaHeap )
    {
      if ( TlsSetValue(LsaDbpDsThreadState, LsaHeap) )
      {
        *(_OWORD *)v1 = 0;
        *((_OWORD *)v1 + 1) = 0;
        *((_QWORD *)v1 + 4) = 0;
        ++v1[1];
      }
      else
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          LastError = GetLastError();
          CurrentThreadId = GetCurrentThreadId();
          WPP_SF_qLL(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, v7, v1, CurrentThreadId, LastError);
        }
        LsapFreeLsaHeap(v1, v3, v4);
        return 0;
      }
    }
  }
  return (struct _LSADS_PER_THREAD_INFO *)v1;
}

```

## disassembly

```asm
0x180015664  mov     [rsp+arg_0], rbx
0x180015669  push    rdi
0x18001566a  sub     rsp, 30h
0x18001566e  mov     ecx, cs:?LsaDbpDsThreadState@@3KA; dwTlsIndex
0x180015674  call    cs:__imp_TlsGetValue
0x18001567a  mov     rdi, rax
0x18001567d  test    rax, rax
0x180015680  jz      short loc_18001568A
0x180015682  inc     dword ptr [rax+4]
0x180015685  jmp     loc_18001570B
0x18001568a  mov     ecx, 28h ; '('
0x18001568f  call    cs:__imp_LsapAllocateLsaHeap
0x180015695  mov     rdi, rax
0x180015698  test    rax, rax
0x18001569b  jz      short loc_18001570B
0x18001569d  mov     ecx, cs:?LsaDbpDsThreadState@@3KA; dwTlsIndex
0x1800156a3  mov     rdx, rax; lpTlsValue
0x1800156a6  call    cs:__imp_TlsSetValue
0x1800156ac  test    eax, eax
0x1800156ae  jnz     short loc_1800156F8
0x1800156b0  mov     rax, cs:WPP_GLOBAL_Control
0x1800156b7  test    byte ptr [rax+1Ch], 1
0x1800156bb  jz      short loc_1800156EB
0x1800156bd  call    cs:__imp_GetLastError
0x1800156c3  mov     ebx, eax
0x1800156c5  call    cs:__imp_GetCurrentThreadId
0x1800156cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800156d2  mov     edx, 0Ah
0x1800156d7  mov     [rsp+38h+var_10], ebx
0x1800156db  mov     r9, rdi
0x1800156de  mov     [rsp+38h+var_18], eax
0x1800156e2  mov     rcx, [rcx+10h]
0x1800156e6  call    WPP_SF_qLL
0x1800156eb  mov     rcx, rdi
0x1800156ee  call    cs:__imp_LsapFreeLsaHeap
0x1800156f4  xor     edi, edi
0x1800156f6  jmp     short loc_18001570B
0x1800156f8  xorps   xmm0, xmm0
0x1800156fb  xor     eax, eax
0x1800156fd  movups  xmmword ptr [rdi], xmm0
0x180015700  movups  xmmword ptr [rdi+10h], xmm0
0x180015704  mov     [rdi+20h], rax
0x180015708  inc     dword ptr [rdi+4]
0x18001570b  mov     rbx, [rsp+38h+arg_0]
0x180015710  mov     rax, rdi
0x180015713  add     rsp, 30h
0x180015717  pop     rdi
0x180015718  retn
```
