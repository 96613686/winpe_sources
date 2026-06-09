# Microsoft::Windows::Performance::CEtwPrivateLogger::StartTraceW(ushort const *,_EVENT_TRACE_PROPERTIES const *,ushort const *,ulong,void *)

- ea: `0x18000c484`
- end: `0x18000c776`
- name: `?StartTraceW@CEtwPrivateLogger@Performance@Windows@Microsoft@@QEAAJPEBGPEBU_EVENT_TRACE_PROPERTIES@@0KPEAX@Z`
- size: `754`
- prototype: `__int64 __usercall@<rax>(Microsoft::Windows::Performance::CEtwPrivateLogger *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, const struct _EVENT_TRACE_PROPERTIES *@<r8>, const unsigned __int16 *@<r9>, unsigned int, void *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18000aa44`

## callees

- `0x1800017e0`
- `0x1800023c0`
- `0x1800029b5`
- `0x1800099b8`
- `0x18000bf04`
- `0x18000c484`
- `0x18000c7f4`
- `0x18000c878`
- `0x18000cba4`
- `0x18000cbc8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000c6e7`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000c721`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000c6e7`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000c721`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000c601`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000c601`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000c53c`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000c53c`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000c527`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000c527`
- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x18000c711`
- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x18000c711`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Performance::CEtwPrivateLogger::StartTraceW(
        Microsoft::Windows::Performance::CEtwPrivateLogger *this,
        const unsigned __int16 *a2,
        const struct _EVENT_TRACE_PROPERTIES *a3,
        const unsigned __int16 *a4,
        unsigned int Size,
        void *Src)
{
  __int64 result; // rax
  unsigned int v8; // edi
  int v9; // ecx
  unsigned __int64 v10; // r15
  unsigned int v11; // esi
  unsigned int v12; // r12d
  void *v13; // rax
  __int128 v14; // xmm1
  __int128 v15; // xmm2
  __int128 v16; // xmm3
  __int128 v17; // xmm4
  __int128 v18; // xmm5
  __int128 v19; // xmm6
  __int64 v20; // xmm7_8
  __int64 v21; // rax
  HRESULT v22; // edi
  ULONG started; // edi
  unsigned int v24[2]; // [rsp+28h] [rbp-99h] BYREF
  const struct _EVENT_TRACE_PROPERTIES *v25; // [rsp+30h] [rbp-91h]
  const unsigned __int16 *pguid; // [rsp+38h] [rbp-89h]
  GUID pguid_8; // [rsp+40h] [rbp-81h] BYREF
  OLECHAR sz[8]; // [rsp+58h] [rbp-69h] BYREF
  __int128 v29; // [rsp+68h] [rbp-59h]
  __int128 v30; // [rsp+78h] [rbp-49h]
  _OWORD v31[2]; // [rsp+88h] [rbp-39h]

  v25 = a3;
  pguid = a2;
  if ( Size && !Src )
    return 2147942487LL;
  *(_OWORD *)sz = *(_OWORD *)L"{28ad2447-105b-4fe2-9599-e59b2aa9a634}";
  v30 = *(_OWORD *)L"fe2-9599-e59b2aa9a634}";
  v29 = *(_OWORD *)L"7-105b-4fe2-9599-e59b2aa9a634}";
  v31[0] = *(_OWORD *)L"-e59b2aa9a634}";
  *(_OWORD *)((char *)v31 + 14) = *(_OWORD *)L"a9a634}";
  pguid_8 = 0;
  CoCreateGuid(&pguid_8);
  StringFromGUID2(&pguid_8, sz, 39);
  v24[0] = 0;
  *(_QWORD *)&pguid_8.Data1 = 0;
  result = StringCchLengthW(sz, 0x400u, (unsigned __int64 *)&pguid_8.Data1);
  if ( (int)result >= 0 )
  {
    result = ULongLongToULong(*(unsigned __int64 *)&pguid_8.Data1, v24);
    if ( (int)result >= 0 )
    {
      v8 = Size + 120;
      if ( Size < 0xFFFFFF88 )
      {
        if ( (v8 & 1) != 0 )
        {
          v9 = v8 & 1;
          if ( v8 - v9 + 2 < v8 )
            return 2147942934LL;
          v8 = v8 - v9 + 2;
        }
        v10 = v24[0];
        pguid_8.Data1 = 0;
        result = ULongLongToULong(2LL * v24[0], &pguid_8.Data1);
        if ( (int)result < 0 )
          return result;
        v11 = v8 + pguid_8.Data1;
        if ( v8 + pguid_8.Data1 >= v8 )
        {
          pguid_8.Data1 = 0;
          result = ULongLongToULong(0x800u, &pguid_8.Data1);
          if ( (int)result < 0 )
            return result;
          v12 = v11 + pguid_8.Data1;
          if ( v11 + pguid_8.Data1 >= v11 )
          {
            v13 = malloc(v12);
            *((_QWORD *)this + 1) = v13;
            if ( !v13 )
              return 2147942414LL;
            memset_0(v13, 0, v12);
            v14 = *(_OWORD *)&v25->Wnode.CountLost;
            v15 = *(_OWORD *)v25->Wnode.Guid.Data4;
            v16 = *(_OWORD *)&v25->BufferSize;
            v17 = *(_OWORD *)&v25->LogFileMode;
            v18 = *(_OWORD *)&v25->NumberOfBuffers;
            v19 = *(_OWORD *)&v25->LogBuffersLost;
            v20 = *(_QWORD *)&v25->LogFileNameOffset;
            v21 = *((_QWORD *)this + 1);
            *(_OWORD *)v21 = *(_OWORD *)&v25->Wnode.BufferSize;
            *(_OWORD *)(v21 + 16) = v14;
            *(_OWORD *)(v21 + 32) = v15;
            *(_OWORD *)(v21 + 48) = v16;
            *(_OWORD *)(v21 + 64) = v17;
            *(_OWORD *)(v21 + 80) = v18;
            *(_OWORD *)(v21 + 96) = v19;
            *(_QWORD *)(v21 + 112) = v20;
            **((_DWORD **)this + 1) = v12;
            *(_DWORD *)(*((_QWORD *)this + 1) + 44LL) = 0x20000;
            *(_DWORD *)(*((_QWORD *)this + 1) + 116LL) = v8;
            *(_DWORD *)(*((_QWORD *)this + 1) + 112LL) = v11;
            if ( Src )
              memcpy_0((void *)(*((_QWORD *)this + 1) + 120LL), Src, Size);
            StringCchCopyNW((unsigned __int16 *)(*((_QWORD *)this + 1) + v8), v10, sz, v10);
            StringCchCopyNW((unsigned __int16 *)(*((_QWORD *)this + 1) + v11), 0x400u, pguid, 0x400u);
            v22 = Microsoft::Windows::Performance::CEtwPrivateLogger::Register(this);
            if ( v22 >= 0 )
            {
              *(_OWORD *)(*((_QWORD *)this + 1) + 24LL) = *((_OWORD *)this + 2);
              started = StartTraceW((PTRACEHANDLE)this, sz, *((PEVENT_TRACE_PROPERTIES *)this + 1));
              if ( started )
              {
                free(*((void **)this + 1));
                *((_QWORD *)this + 1) = 0;
                Microsoft::Windows::Performance::CEtwPrivateLogger::Unregister(this);
              }
              return ATL::AtlHresultFromWin32(started);
            }
            else
            {
              free(*((void **)this + 1));
              result = (unsigned int)v22;
              *((_QWORD *)this + 1) = 0;
            }
            return result;
          }
        }
      }
      return 2147942934LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000c484  mov     rax, rsp
0x18000c487  mov     [rax+18h], rbx
0x18000c48b  push    rbp
0x18000c48c  push    rsi
0x18000c48d  push    rdi
0x18000c48e  push    r12
0x18000c490  push    r13
0x18000c492  push    r14
0x18000c494  push    r15
0x18000c496  lea     rbp, [rax-4Fh]
0x18000c49a  sub     rsp, 0D0h
0x18000c4a1  movaps  xmmword ptr [rax-48h], xmm6
0x18000c4a5  movaps  xmmword ptr [rax-58h], xmm7
0x18000c4a9  mov     rax, cs:__security_cookie
0x18000c4b0  xor     rax, rsp
0x18000c4b3  mov     [rbp+47h+var_60], rax
0x18000c4b7  mov     r14d, dword ptr [rbp+47h+Size]
0x18000c4bb  xor     r12d, r12d
0x18000c4be  mov     r13, [rbp+47h+Src]
0x18000c4c2  mov     rbx, rcx
0x18000c4c5  mov     [rsp+100h+var_D8], r8
0x18000c4ca  mov     qword ptr [rsp+100h+pguid.Data1], rdx
0x18000c4cf  test    r14d, r14d
0x18000c4d2  jz      short loc_18000C4E3
0x18000c4d4  test    r13, r13
0x18000c4d7  jnz     short loc_18000C4E3
0x18000c4d9  mov     eax, 80070057h
0x18000c4de  jmp     loc_18000C745
0x18000c4e3  movaps  xmm0, xmmword ptr cs:a28ad2447105b4f; "{28ad2447-105b-4fe2-9599-e59b2aa9a634}"
0x18000c4ea  lea     rcx, [rsp+100h+pguid.Data4]; pguid
0x18000c4ef  movaps  xmm1, xmmword ptr cs:a28ad2447105b4f+10h; "7-105b-4fe2-9599-e59b2aa9a634}"
0x18000c4f6  movaps  xmmword ptr [rbp+47h+sz], xmm0
0x18000c4fa  movaps  xmm0, xmmword ptr cs:a28ad2447105b4f+20h; "fe2-9599-e59b2aa9a634}"
0x18000c501  movaps  [rbp+47h+var_90], xmm0
0x18000c505  movups  xmm0, xmmword ptr cs:a28ad2447105b4f+3Eh; "a9a634}"
0x18000c50c  movaps  [rbp+47h+var_A0], xmm1
0x18000c510  movaps  xmm1, xmmword ptr cs:a28ad2447105b4f+30h; "-e59b2aa9a634}"
0x18000c517  movaps  xmmword ptr [rbp+47h+var_80], xmm1
0x18000c51b  movups  xmmword ptr [rbp+47h+var_80+0Eh], xmm0
0x18000c51f  xorps   xmm0, xmm0
0x18000c522  movups  xmmword ptr [rsp+100h+pguid.Data4], xmm0
0x18000c527  call    cs:__imp_CoCreateGuid
0x18000c52d  mov     r8d, 27h ; '''; cchMax
0x18000c533  lea     rdx, [rbp+47h+sz]; lpsz
0x18000c537  lea     rcx, [rsp+100h+pguid.Data4]; rguid
0x18000c53c  call    cs:__imp_StringFromGUID2
0x18000c542  lea     r8, [rsp+100h+pguid.Data4]; unsigned __int64 *
0x18000c547  mov     [rsp+100h+var_E0], r12d
0x18000c54c  mov     edx, 400h; unsigned __int64
0x18000c551  mov     qword ptr [rsp+100h+pguid.Data4], r12
0x18000c556  lea     rcx, [rbp+47h+sz]; unsigned __int16 *
0x18000c55a  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18000c55f  test    eax, eax
0x18000c561  js      loc_18000C745
0x18000c567  mov     rcx, qword ptr [rsp+100h+pguid.Data4]; unsigned __int64
0x18000c56c  lea     rdx, [rsp+100h+var_E0]; unsigned int *
0x18000c571  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18000c576  test    eax, eax
0x18000c578  js      loc_18000C745
0x18000c57e  lea     edi, [r14+78h]
0x18000c582  cmp     edi, 78h ; 'x'
0x18000c585  jb      loc_18000C740
0x18000c58b  mov     ecx, edi
0x18000c58d  and     ecx, 1
0x18000c590  jz      short loc_18000C5A3
0x18000c592  mov     eax, edi
0x18000c594  sub     eax, ecx
0x18000c596  add     eax, 2
0x18000c599  cmp     eax, edi
0x18000c59b  jb      loc_18000C740
0x18000c5a1  mov     edi, eax
0x18000c5a3  mov     r15d, [rsp+100h+var_E0]
0x18000c5a8  lea     rdx, [rsp+100h+pguid.Data4]; unsigned int *
0x18000c5ad  mov     dword ptr [rsp+100h+pguid.Data4], r12d
0x18000c5b2  lea     rcx, [r15+r15]; unsigned __int64
0x18000c5b6  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18000c5bb  test    eax, eax
0x18000c5bd  js      loc_18000C745
0x18000c5c3  mov     esi, dword ptr [rsp+100h+pguid.Data4]
0x18000c5c7  add     esi, edi
0x18000c5c9  cmp     esi, edi
0x18000c5cb  jb      loc_18000C740
0x18000c5d1  lea     rdx, [rsp+100h+pguid.Data4]; unsigned int *
0x18000c5d6  mov     dword ptr [rsp+100h+pguid.Data4], r12d
0x18000c5db  mov     ecx, 800h; unsigned __int64
0x18000c5e0  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18000c5e5  test    eax, eax
0x18000c5e7  js      loc_18000C745
0x18000c5ed  mov     r12d, dword ptr [rsp+100h+pguid.Data4]
0x18000c5f2  add     r12d, esi
0x18000c5f5  cmp     r12d, esi
0x18000c5f8  jb      loc_18000C740
0x18000c5fe  mov     ecx, r12d; Size
0x18000c601  call    cs:__imp_malloc
0x18000c607  mov     [rbx+8], rax
0x18000c60b  test    rax, rax
0x18000c60e  jnz     short loc_18000C61A
0x18000c610  mov     eax, 8007000Eh
0x18000c615  jmp     loc_18000C745
0x18000c61a  mov     r8d, r12d; Size
0x18000c61d  xor     edx, edx; Val
0x18000c61f  mov     rcx, rax; void *
0x18000c622  call    memset_0
0x18000c627  mov     rax, [rsp+100h+var_D8]
0x18000c62c  movaps  xmm0, xmmword ptr [rax]
0x18000c62f  movaps  xmm1, xmmword ptr [rax+10h]
0x18000c633  movaps  xmm2, xmmword ptr [rax+20h]
0x18000c637  movaps  xmm3, xmmword ptr [rax+30h]
0x18000c63b  movaps  xmm4, xmmword ptr [rax+40h]
0x18000c63f  movaps  xmm5, xmmword ptr [rax+50h]
0x18000c643  movaps  xmm6, xmmword ptr [rax+60h]
0x18000c647  movsd   xmm7, qword ptr [rax+70h]
0x18000c64c  mov     rax, [rbx+8]
0x18000c650  movups  xmmword ptr [rax], xmm0
0x18000c653  movups  xmmword ptr [rax+10h], xmm1
0x18000c657  movups  xmmword ptr [rax+20h], xmm2
0x18000c65b  movups  xmmword ptr [rax+30h], xmm3
0x18000c65f  movups  xmmword ptr [rax+40h], xmm4
0x18000c663  movups  xmmword ptr [rax+50h], xmm5
0x18000c667  movups  xmmword ptr [rax+60h], xmm6
0x18000c66b  movsd   qword ptr [rax+70h], xmm7
0x18000c670  mov     rax, [rbx+8]
0x18000c674  mov     [rax], r12d
0x18000c677  mov     rax, [rbx+8]
0x18000c67b  mov     dword ptr [rax+2Ch], 20000h
0x18000c682  mov     rax, [rbx+8]
0x18000c686  mov     [rax+74h], edi
0x18000c689  mov     rax, [rbx+8]
0x18000c68d  mov     [rax+70h], esi
0x18000c690  test    r13, r13
0x18000c693  jz      short loc_18000C6A8
0x18000c695  mov     rcx, [rbx+8]
0x18000c699  mov     r8, r14; Size
0x18000c69c  add     rcx, 78h ; 'x'; void *
0x18000c6a0  mov     rdx, r13; Src
0x18000c6a3  call    memcpy_0
0x18000c6a8  mov     ecx, edi
0x18000c6aa  lea     r8, [rbp+47h+sz]; unsigned __int16 *
0x18000c6ae  add     rcx, [rbx+8]; unsigned __int16 *
0x18000c6b2  mov     r9, r15; unsigned __int64
0x18000c6b5  mov     rdx, r15; unsigned __int64
0x18000c6b8  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18000c6bd  mov     r8, qword ptr [rsp+100h+pguid.Data1]; unsigned __int16 *
0x18000c6c2  mov     edx, 400h; unsigned __int64
0x18000c6c7  mov     ecx, esi
0x18000c6c9  mov     r9d, edx; unsigned __int64
0x18000c6cc  add     rcx, [rbx+8]; unsigned __int16 *
0x18000c6d0  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18000c6d5  mov     rcx, rbx; this
0x18000c6d8  call    ?Register@CEtwPrivateLogger@Performance@Windows@Microsoft@@AEAAJXZ; Microsoft::Windows::Performance::CEtwPrivateLogger::Register(void)
0x18000c6dd  mov     edi, eax
0x18000c6df  test    eax, eax
0x18000c6e1  jns     short loc_18000C6F9
0x18000c6e3  mov     rcx, [rbx+8]; Block
0x18000c6e7  call    cs:__imp_free
0x18000c6ed  mov     eax, edi
0x18000c6ef  mov     qword ptr [rbx+8], 0
0x18000c6f7  jmp     short loc_18000C745
0x18000c6f9  mov     rax, [rbx+8]
0x18000c6fd  lea     rdx, [rbp+47h+sz]; InstanceName
0x18000c701  movups  xmm0, xmmword ptr [rbx+20h]
0x18000c705  mov     rcx, rbx; TraceHandle
0x18000c708  movdqu  xmmword ptr [rax+18h], xmm0
0x18000c70d  mov     r8, [rbx+8]; Properties
0x18000c711  call    cs:__imp_StartTraceW
0x18000c717  mov     edi, eax
0x18000c719  test    eax, eax
0x18000c71b  jz      short loc_18000C737
0x18000c71d  mov     rcx, [rbx+8]; Block
0x18000c721  call    cs:__imp_free
0x18000c727  mov     rcx, rbx; this
0x18000c72a  mov     qword ptr [rbx+8], 0
0x18000c732  call    ?Unregister@CEtwPrivateLogger@Performance@Windows@Microsoft@@AEAAJXZ; Microsoft::Windows::Performance::CEtwPrivateLogger::Unregister(void)
0x18000c737  mov     ecx, edi; unsigned int
0x18000c739  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x18000c73e  jmp     short loc_18000C745
0x18000c740  mov     eax, 80070216h
0x18000c745  mov     rcx, [rbp+47h+var_60]
0x18000c749  xor     rcx, rsp; StackCookie
0x18000c74c  call    __security_check_cookie
0x18000c751  lea     r11, [rsp+100h+var_30]
0x18000c759  mov     rbx, [r11+50h]
0x18000c75d  movaps  xmm6, xmmword ptr [r11-10h]
0x18000c762  movaps  xmm7, xmmword ptr [r11-20h]
0x18000c767  mov     rsp, r11
0x18000c76a  pop     r15
0x18000c76c  pop     r14
0x18000c76e  pop     r13
0x18000c770  pop     r12
0x18000c772  pop     rdi
0x18000c773  pop     rsi
0x18000c774  pop     rbp
0x18000c775  retn
```
