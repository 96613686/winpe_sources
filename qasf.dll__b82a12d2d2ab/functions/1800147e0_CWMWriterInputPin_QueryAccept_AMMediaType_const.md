# CWMWriterInputPin::QueryAccept(_AMMediaType const *)

- ea: `0x1800147e0`
- end: `0x180014985`
- name: `?QueryAccept@CWMWriterInputPin@@UEAAJPEBU_AMMediaType@@@Z`
- size: `421`
- prototype: `__int64 __fastcall(CWMWriterInputPin *__hidden this, const struct _AMMediaType *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180005790`
- `0x1800147e0`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1800147fd`
- `KERNEL32!EnterCriticalSection` at `0x1800147fd`
- `KERNEL32!LeaveCriticalSection` at `0x1800148cb`
- `KERNEL32!LeaveCriticalSection` at `0x1800148cb`

## pseudocode

```c
__int64 __fastcall CWMWriterInputPin::QueryAccept(CWMWriterInputPin *this, const struct _AMMediaType *a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbp
  unsigned int v5; // esi

  v2 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)this + 40);
  EnterCriticalSection(v2 + 6);
  if ( !*(_DWORD *)(*((_QWORD *)this + 40) + 40LL)
    || *((_QWORD *)this + 10) == *(_QWORD *)&MEDIATYPE_Audio.Data1
    && *((_QWORD *)this + 11) == *(_QWORD *)MEDIATYPE_Audio.Data4
    && *(_QWORD *)&a2->majortype.Data1 == *(_QWORD *)&MEDIATYPE_Audio.Data1
    && *(_QWORD *)a2->majortype.Data4 == *(_QWORD *)MEDIATYPE_Audio.Data4
    && *(_QWORD *)&a2->formattype.Data1 == *(_QWORD *)&FORMAT_WaveFormatEx.Data1
    && *(_QWORD *)a2->formattype.Data4 == *(_QWORD *)FORMAT_WaveFormatEx.Data4
    || *((_QWORD *)this + 10) == *(_QWORD *)&MEDIATYPE_Interleaved.Data1
    && *((_QWORD *)this + 11) == *(_QWORD *)MEDIATYPE_Interleaved.Data4
    && *(_QWORD *)&a2->majortype.Data1 == *(_QWORD *)&MEDIATYPE_Interleaved.Data1
    && *(_QWORD *)a2->majortype.Data4 == *(_QWORD *)MEDIATYPE_Interleaved.Data4
    && *(_QWORD *)&a2->formattype.Data1 == *(_QWORD *)&FORMAT_DvInfo.Data1
    && *(_QWORD *)a2->formattype.Data4 == *(_QWORD *)FORMAT_DvInfo.Data4
    && *((_DWORD *)this + 38) == a2->cbFormat
    && a2->pbFormat
    || (v5 = 1, *(_QWORD *)&a2->majortype.Data1 == *(_QWORD *)&MEDIATYPE_ScriptCommand.Data1)
    && *(_QWORD *)a2->majortype.Data4 == *(_QWORD *)MEDIATYPE_ScriptCommand.Data4 )
  {
    v5 = 0;
  }
  LeaveCriticalSection(v2 + 6);
  if ( *(_QWORD *)&MEDIATYPE_Video.Data1 == *(_QWORD *)&a2->majortype.Data1
    && *(_QWORD *)MEDIATYPE_Video.Data4 == *(_QWORD *)a2->majortype.Data4
    && *(_QWORD *)&FORMAT_VideoInfo2.Data1 == *(_QWORD *)&a2->formattype.Data1
    && *(_QWORD *)FORMAT_VideoInfo2.Data4 == *(_QWORD *)a2->formattype.Data4
    && *((_QWORD *)this + 10) == *(_QWORD *)&a2->majortype.Data1
    && *((_QWORD *)this + 11) == *(_QWORD *)a2->majortype.Data4
    && *((_QWORD *)this + 12) == *(_QWORD *)&a2->subtype.Data1
    && *((_QWORD *)this + 13) == *(_QWORD *)a2->subtype.Data4
    && *((_DWORD *)this + 28) == a2->bFixedSizeSamples
    && *((_DWORD *)this + 29) == a2->bTemporalCompression
    && *((_DWORD *)this + 30) == a2->lSampleSize
    && *(_QWORD *)((char *)this + 124) == *(_QWORD *)&a2->formattype.Data1
    && *(_QWORD *)((char *)this + 132) == *(_QWORD *)a2->formattype.Data4
    && *((_DWORD *)this + 38) == a2->cbFormat
    || !v5 )
  {
    return (unsigned int)CBasePin::QueryAccept(this, a2);
  }
  return v5;
}

```

## disassembly

```asm
0x1800147e0  push    rbx
0x1800147e2  push    rbp
0x1800147e3  push    rsi
0x1800147e4  push    rdi
0x1800147e5  sub     rsp, 28h
0x1800147e9  mov     rbp, [rcx+140h]
0x1800147f0  mov     rdi, rcx
0x1800147f3  mov     rbx, rdx
0x1800147f6  lea     rcx, [rbp+0F0h]; lpCriticalSection
0x1800147fd  call    cs:__imp_EnterCriticalSection
0x180014803  mov     rax, [rdi+140h]
0x18001480a  cmp     dword ptr [rax+28h], 0
0x18001480e  jz      loc_1800148C2
0x180014814  mov     rax, qword ptr cs:MEDIATYPE_Audio.Data1
0x18001481b  cmp     [rdi+50h], rax
0x18001481f  jnz     short loc_180014853
0x180014821  mov     rcx, qword ptr cs:MEDIATYPE_Audio.Data4
0x180014828  cmp     [rdi+58h], rcx
0x18001482c  jnz     short loc_180014853
0x18001482e  cmp     [rbx], rax
0x180014831  jnz     short loc_180014853
0x180014833  cmp     [rbx+8], rcx
0x180014837  jnz     short loc_180014853
0x180014839  mov     rax, [rbx+2Ch]
0x18001483d  cmp     rax, qword ptr cs:FORMAT_WaveFormatEx.Data1
0x180014844  jnz     short loc_180014853
0x180014846  mov     rax, [rbx+34h]
0x18001484a  cmp     rax, qword ptr cs:FORMAT_WaveFormatEx.Data4
0x180014851  jz      short loc_1800148C2
0x180014853  mov     rcx, qword ptr cs:MEDIATYPE_Interleaved.Data1
0x18001485a  cmp     [rdi+50h], rcx
0x18001485e  jnz     short loc_1800148A4
0x180014860  mov     rax, qword ptr cs:MEDIATYPE_Interleaved.Data4
0x180014867  cmp     [rdi+58h], rax
0x18001486b  jnz     short loc_1800148A4
0x18001486d  cmp     [rbx], rcx
0x180014870  jnz     short loc_1800148A4
0x180014872  cmp     [rbx+8], rax
0x180014876  jnz     short loc_1800148A4
0x180014878  mov     rax, [rbx+2Ch]
0x18001487c  cmp     rax, qword ptr cs:FORMAT_DvInfo.Data1
0x180014883  jnz     short loc_1800148A4
0x180014885  mov     rax, [rbx+34h]
0x180014889  cmp     rax, qword ptr cs:FORMAT_DvInfo.Data4
0x180014890  jnz     short loc_1800148A4
0x180014892  mov     eax, [rbx+48h]
0x180014895  cmp     [rdi+98h], eax
0x18001489b  jnz     short loc_1800148A4
0x18001489d  cmp     qword ptr [rbx+50h], 0
0x1800148a2  jnz     short loc_1800148C2
0x1800148a4  mov     rax, [rbx]
0x1800148a7  mov     esi, 1
0x1800148ac  cmp     rax, qword ptr cs:MEDIATYPE_ScriptCommand.Data1
0x1800148b3  jnz     short loc_1800148C4
0x1800148b5  mov     rax, [rbx+8]
0x1800148b9  cmp     rax, qword ptr cs:MEDIATYPE_ScriptCommand.Data4
0x1800148c0  jnz     short loc_1800148C4
0x1800148c2  xor     esi, esi
0x1800148c4  lea     rcx, [rbp+0F0h]; lpCriticalSection
0x1800148cb  call    cs:__imp_LeaveCriticalSection
0x1800148d1  mov     rax, qword ptr cs:MEDIATYPE_Video.Data1
0x1800148d8  cmp     rax, [rbx]
0x1800148db  jnz     loc_180014969
0x1800148e1  mov     rax, qword ptr cs:MEDIATYPE_Video.Data4
0x1800148e8  cmp     rax, [rbx+8]
0x1800148ec  jnz     short loc_180014969
0x1800148ee  mov     rax, qword ptr cs:FORMAT_VideoInfo2.Data1
0x1800148f5  cmp     rax, [rbx+2Ch]
0x1800148f9  jnz     short loc_180014969
0x1800148fb  mov     rax, qword ptr cs:FORMAT_VideoInfo2.Data4
0x180014902  cmp     rax, [rbx+34h]
0x180014906  jnz     short loc_180014969
0x180014908  mov     rax, [rdi+50h]
0x18001490c  cmp     rax, [rbx]
0x18001490f  jnz     short loc_180014969
0x180014911  mov     rax, [rdi+58h]
0x180014915  cmp     rax, [rbx+8]
0x180014919  jnz     short loc_180014969
0x18001491b  mov     rax, [rdi+60h]
0x18001491f  cmp     rax, [rbx+10h]
0x180014923  jnz     short loc_180014969
0x180014925  mov     rax, [rdi+68h]
0x180014929  cmp     rax, [rbx+18h]
0x18001492d  jnz     short loc_180014969
0x18001492f  mov     eax, [rbx+20h]
0x180014932  cmp     [rdi+70h], eax
0x180014935  jnz     short loc_180014969
0x180014937  mov     eax, [rbx+24h]
0x18001493a  cmp     [rdi+74h], eax
0x18001493d  jnz     short loc_180014969
0x18001493f  mov     eax, [rbx+28h]
0x180014942  cmp     [rdi+78h], eax
0x180014945  jnz     short loc_180014969
0x180014947  mov     rax, [rdi+7Ch]
0x18001494b  cmp     rax, [rbx+2Ch]
0x18001494f  jnz     short loc_180014969
0x180014951  mov     rax, [rdi+84h]
0x180014958  cmp     rax, [rbx+34h]
0x18001495c  jnz     short loc_180014969
0x18001495e  mov     eax, [rbx+48h]
0x180014961  cmp     [rdi+98h], eax
0x180014967  jz      short loc_18001496D
0x180014969  test    esi, esi
0x18001496b  jnz     short loc_18001497A
0x18001496d  mov     rdx, rbx; struct _AMMediaType *
0x180014970  mov     rcx, rdi; this
0x180014973  call    ?QueryAccept@CBasePin@@UEAAJPEBU_AMMediaType@@@Z; CBasePin::QueryAccept(_AMMediaType const *)
0x180014978  mov     esi, eax
0x18001497a  mov     eax, esi
0x18001497c  add     rsp, 28h
0x180014980  pop     rdi
0x180014981  pop     rsi
0x180014982  pop     rbp
0x180014983  pop     rbx
0x180014984  retn
```
