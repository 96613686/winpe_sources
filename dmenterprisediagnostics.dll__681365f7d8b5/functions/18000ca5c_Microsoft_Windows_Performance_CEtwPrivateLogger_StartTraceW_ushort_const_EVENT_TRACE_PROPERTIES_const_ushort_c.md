# Microsoft::Windows::Performance::CEtwPrivateLogger::StartTraceW(ushort const *,_EVENT_TRACE_PROPERTIES const *,ushort const *,ulong,void *)

- ea: `0x18000ca5c`
- end: `0x18000cd73`
- name: `?StartTraceW@CEtwPrivateLogger@Performance@Windows@Microsoft@@QEAAJPEBGPEBU_EVENT_TRACE_PROPERTIES@@0KPEAX@Z`
- size: `791`
- prototype: `__int64 __usercall@<rax>(Microsoft::Windows::Performance::CEtwPrivateLogger *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, const struct _EVENT_TRACE_PROPERTIES *@<r8>, const unsigned __int16 *@<r9>, unsigned int, void *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18000afdc`

## callees

- `0x180001800`
- `0x1800023e0`
- `0x1800029d5`
- `0x180009e98`
- `0x18000c488`
- `0x18000ca5c`
- `0x18000ce00`
- `0x18000ce84`
- `0x18000d1d4`
- `0x18000d1fc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000ccd1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000cd17`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000ccd1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000cd17`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000cbe5`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000cbe5`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000cb1a`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000cb1a`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000caff`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000caff`
- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x18000cd01`
- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x18000cd01`

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
0x18000ca5c  mov     rax, rsp
0x18000ca5f  mov     [rax+18h], rbx
0x18000ca63  push    rbp
0x18000ca64  push    rsi
0x18000ca65  push    rdi
0x18000ca66  push    r12
0x18000ca68  push    r13
0x18000ca6a  push    r14
0x18000ca6c  push    r15
0x18000ca6e  lea     rbp, [rax-4Fh]
0x18000ca72  sub     rsp, 0D0h
0x18000ca79  movaps  xmmword ptr [rax-48h], xmm6
0x18000ca7d  movaps  xmmword ptr [rax-58h], xmm7
0x18000ca81  mov     rax, cs:__security_cookie
0x18000ca88  xor     rax, rsp
0x18000ca8b  mov     [rbp+47h+var_60], rax
0x18000ca8f  mov     r14d, dword ptr [rbp+47h+Size]
0x18000ca93  xor     r12d, r12d
0x18000ca96  mov     r13, [rbp+47h+Src]
0x18000ca9a  mov     rbx, rcx
0x18000ca9d  mov     [rsp+100h+var_D8], r8
0x18000caa2  mov     qword ptr [rsp+100h+pguid.Data1], rdx
0x18000caa7  test    r14d, r14d
0x18000caaa  jz      short loc_18000CABB
0x18000caac  test    r13, r13
0x18000caaf  jnz     short loc_18000CABB
0x18000cab1  mov     eax, 80070057h
0x18000cab6  jmp     loc_18000CD41
0x18000cabb  movaps  xmm0, xmmword ptr cs:a28ad2447105b4f; "{28ad2447-105b-4fe2-9599-e59b2aa9a634}"
0x18000cac2  lea     rcx, [rsp+100h+pguid.Data4]; pguid
0x18000cac7  movaps  xmm1, xmmword ptr cs:a28ad2447105b4f+10h; "7-105b-4fe2-9599-e59b2aa9a634}"
0x18000cace  movaps  xmmword ptr [rbp+47h+sz], xmm0
0x18000cad2  movaps  xmm0, xmmword ptr cs:a28ad2447105b4f+20h; "fe2-9599-e59b2aa9a634}"
0x18000cad9  movaps  [rbp+47h+var_90], xmm0
0x18000cadd  movups  xmm0, xmmword ptr cs:a28ad2447105b4f+3Eh; "a9a634}"
0x18000cae4  movaps  [rbp+47h+var_A0], xmm1
0x18000cae8  movaps  xmm1, xmmword ptr cs:a28ad2447105b4f+30h; "-e59b2aa9a634}"
0x18000caef  movaps  xmmword ptr [rbp+47h+var_80], xmm1
0x18000caf3  movups  xmmword ptr [rbp+47h+var_80+0Eh], xmm0
0x18000caf7  xorps   xmm0, xmm0
0x18000cafa  movups  xmmword ptr [rsp+100h+pguid.Data4], xmm0
0x18000caff  call    cs:__imp_CoCreateGuid
0x18000cb06  nop     dword ptr [rax+rax+00h]
0x18000cb0b  mov     r8d, 27h ; '''; cchMax
0x18000cb11  lea     rdx, [rbp+47h+sz]; lpsz
0x18000cb15  lea     rcx, [rsp+100h+pguid.Data4]; rguid
0x18000cb1a  call    cs:__imp_StringFromGUID2
0x18000cb21  nop     dword ptr [rax+rax+00h]
0x18000cb26  lea     r8, [rsp+100h+pguid.Data4]; unsigned __int64 *
0x18000cb2b  mov     [rsp+100h+var_E0], r12d
0x18000cb30  mov     edx, 400h; unsigned __int64
0x18000cb35  mov     qword ptr [rsp+100h+pguid.Data4], r12
0x18000cb3a  lea     rcx, [rbp+47h+sz]; unsigned __int16 *
0x18000cb3e  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18000cb43  test    eax, eax
0x18000cb45  js      loc_18000CD41
0x18000cb4b  mov     rcx, qword ptr [rsp+100h+pguid.Data4]; unsigned __int64
0x18000cb50  lea     rdx, [rsp+100h+var_E0]; unsigned int *
0x18000cb55  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18000cb5a  test    eax, eax
0x18000cb5c  js      loc_18000CD41
0x18000cb62  lea     edi, [r14+78h]
0x18000cb66  cmp     edi, 78h ; 'x'
0x18000cb69  jb      loc_18000CD3C
0x18000cb6f  mov     ecx, edi
0x18000cb71  and     ecx, 1
0x18000cb74  jz      short loc_18000CB87
0x18000cb76  mov     eax, edi
0x18000cb78  sub     eax, ecx
0x18000cb7a  add     eax, 2
0x18000cb7d  cmp     eax, edi
0x18000cb7f  jb      loc_18000CD3C
0x18000cb85  mov     edi, eax
0x18000cb87  mov     r15d, [rsp+100h+var_E0]
0x18000cb8c  lea     rdx, [rsp+100h+pguid.Data4]; unsigned int *
0x18000cb91  mov     dword ptr [rsp+100h+pguid.Data4], r12d
0x18000cb96  lea     rcx, [r15+r15]; unsigned __int64
0x18000cb9a  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18000cb9f  test    eax, eax
0x18000cba1  js      loc_18000CD41
0x18000cba7  mov     esi, dword ptr [rsp+100h+pguid.Data4]
0x18000cbab  add     esi, edi
0x18000cbad  cmp     esi, edi
0x18000cbaf  jb      loc_18000CD3C
0x18000cbb5  lea     rdx, [rsp+100h+pguid.Data4]; unsigned int *
0x18000cbba  mov     dword ptr [rsp+100h+pguid.Data4], r12d
0x18000cbbf  mov     ecx, 800h; unsigned __int64
0x18000cbc4  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18000cbc9  test    eax, eax
0x18000cbcb  js      loc_18000CD41
0x18000cbd1  mov     r12d, dword ptr [rsp+100h+pguid.Data4]
0x18000cbd6  add     r12d, esi
0x18000cbd9  cmp     r12d, esi
0x18000cbdc  jb      loc_18000CD3C
0x18000cbe2  mov     ecx, r12d; Size
0x18000cbe5  call    cs:__imp_malloc
0x18000cbec  nop     dword ptr [rax+rax+00h]
0x18000cbf1  mov     [rbx+8], rax
0x18000cbf5  test    rax, rax
0x18000cbf8  jnz     short loc_18000CC04
0x18000cbfa  mov     eax, 8007000Eh
0x18000cbff  jmp     loc_18000CD41
0x18000cc04  mov     r8d, r12d; Size
0x18000cc07  xor     edx, edx; Val
0x18000cc09  mov     rcx, rax; void *
0x18000cc0c  call    memset_0
0x18000cc11  mov     rax, [rsp+100h+var_D8]
0x18000cc16  movaps  xmm0, xmmword ptr [rax]
0x18000cc19  movaps  xmm1, xmmword ptr [rax+10h]
0x18000cc1d  movaps  xmm2, xmmword ptr [rax+20h]
0x18000cc21  movaps  xmm3, xmmword ptr [rax+30h]
0x18000cc25  movaps  xmm4, xmmword ptr [rax+40h]
0x18000cc29  movaps  xmm5, xmmword ptr [rax+50h]
0x18000cc2d  movaps  xmm6, xmmword ptr [rax+60h]
0x18000cc31  movsd   xmm7, qword ptr [rax+70h]
0x18000cc36  mov     rax, [rbx+8]
0x18000cc3a  movups  xmmword ptr [rax], xmm0
0x18000cc3d  movups  xmmword ptr [rax+10h], xmm1
0x18000cc41  movups  xmmword ptr [rax+20h], xmm2
0x18000cc45  movups  xmmword ptr [rax+30h], xmm3
0x18000cc49  movups  xmmword ptr [rax+40h], xmm4
0x18000cc4d  movups  xmmword ptr [rax+50h], xmm5
0x18000cc51  movups  xmmword ptr [rax+60h], xmm6
0x18000cc55  movsd   qword ptr [rax+70h], xmm7
0x18000cc5a  mov     rax, [rbx+8]
0x18000cc5e  mov     [rax], r12d
0x18000cc61  mov     rax, [rbx+8]
0x18000cc65  mov     dword ptr [rax+2Ch], 20000h
0x18000cc6c  mov     rax, [rbx+8]
0x18000cc70  mov     [rax+74h], edi
0x18000cc73  mov     rax, [rbx+8]
0x18000cc77  mov     [rax+70h], esi
0x18000cc7a  test    r13, r13
0x18000cc7d  jz      short loc_18000CC92
0x18000cc7f  mov     rcx, [rbx+8]
0x18000cc83  mov     r8, r14; Size
0x18000cc86  add     rcx, 78h ; 'x'; void *
0x18000cc8a  mov     rdx, r13; Src
0x18000cc8d  call    memcpy_0
0x18000cc92  mov     ecx, edi
0x18000cc94  lea     r8, [rbp+47h+sz]; unsigned __int16 *
0x18000cc98  add     rcx, [rbx+8]; unsigned __int16 *
0x18000cc9c  mov     r9, r15; unsigned __int64
0x18000cc9f  mov     rdx, r15; unsigned __int64
0x18000cca2  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18000cca7  mov     r8, qword ptr [rsp+100h+pguid.Data1]; unsigned __int16 *
0x18000ccac  mov     edx, 400h; unsigned __int64
0x18000ccb1  mov     ecx, esi
0x18000ccb3  mov     r9d, edx; unsigned __int64
0x18000ccb6  add     rcx, [rbx+8]; unsigned __int16 *
0x18000ccba  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18000ccbf  mov     rcx, rbx; this
0x18000ccc2  call    ?Register@CEtwPrivateLogger@Performance@Windows@Microsoft@@AEAAJXZ; Microsoft::Windows::Performance::CEtwPrivateLogger::Register(void)
0x18000ccc7  mov     edi, eax
0x18000ccc9  test    eax, eax
0x18000cccb  jns     short loc_18000CCE9
0x18000cccd  mov     rcx, [rbx+8]; Block
0x18000ccd1  call    cs:__imp_free
0x18000ccd8  nop     dword ptr [rax+rax+00h]
0x18000ccdd  mov     eax, edi
0x18000ccdf  mov     qword ptr [rbx+8], 0
0x18000cce7  jmp     short loc_18000CD41
0x18000cce9  mov     rax, [rbx+8]
0x18000cced  lea     rdx, [rbp+47h+sz]; InstanceName
0x18000ccf1  movups  xmm0, xmmword ptr [rbx+20h]
0x18000ccf5  mov     rcx, rbx; TraceHandle
0x18000ccf8  movdqu  xmmword ptr [rax+18h], xmm0
0x18000ccfd  mov     r8, [rbx+8]; Properties
0x18000cd01  call    cs:__imp_StartTraceW
0x18000cd08  nop     dword ptr [rax+rax+00h]
0x18000cd0d  mov     edi, eax
0x18000cd0f  test    eax, eax
0x18000cd11  jz      short loc_18000CD33
0x18000cd13  mov     rcx, [rbx+8]; Block
0x18000cd17  call    cs:__imp_free
0x18000cd1e  nop     dword ptr [rax+rax+00h]
0x18000cd23  mov     rcx, rbx; this
0x18000cd26  mov     qword ptr [rbx+8], 0
0x18000cd2e  call    ?Unregister@CEtwPrivateLogger@Performance@Windows@Microsoft@@AEAAJXZ; Microsoft::Windows::Performance::CEtwPrivateLogger::Unregister(void)
0x18000cd33  mov     ecx, edi; unsigned int
0x18000cd35  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x18000cd3a  jmp     short loc_18000CD41
0x18000cd3c  mov     eax, 80070216h
0x18000cd41  mov     rcx, [rbp+47h+var_60]
0x18000cd45  xor     rcx, rsp; StackCookie
0x18000cd48  call    __security_check_cookie
0x18000cd4d  lea     r11, [rsp+100h+var_30]
0x18000cd55  mov     rbx, [r11+50h]
0x18000cd59  movaps  xmm6, xmmword ptr [r11-10h]
0x18000cd5e  movaps  xmm7, xmmword ptr [r11-20h]
0x18000cd63  mov     rsp, r11
0x18000cd66  pop     r15
0x18000cd68  pop     r14
0x18000cd6a  pop     r13
0x18000cd6c  pop     r12
0x18000cd6e  pop     rdi
0x18000cd6f  pop     rsi
0x18000cd70  pop     rbp
0x18000cd71  retn
```
