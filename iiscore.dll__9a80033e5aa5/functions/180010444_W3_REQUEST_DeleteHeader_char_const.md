# W3_REQUEST::DeleteHeader(char const *)

- ea: `0x180010444`
- end: `0x180010578`
- name: `?DeleteHeader@W3_REQUEST@@QEAAJPEBD@Z`
- size: `308`
- prototype: `int(W3_REQUEST *__hidden this, const char *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180022a40`
- `0x18002701c`

## callees

- `0x180008930`
- `0x180010444`
- `0x1800106c0`
- `0x180027e10`
- `0x18003438e`

## import_xrefs

- `msvcrt!_stricmp` at `0x180010524`
- `msvcrt!_stricmp` at `0x180010524`

## pseudocode

```c
__int64 __fastcall W3_REQUEST::DeleteHeader(W3_REQUEST *this, const char *a2)
{
  __int64 v4; // rcx
  __int64 Key; // rax
  __int64 v6; // rcx
  __int64 v8; // rdx
  __int64 v9; // rdi

  if ( !a2 )
    return 2147942487LL;
  ++*((_DWORD *)this + 12);
  v4 = *((_QWORD *)this + 14);
  if ( *(_BYTE *)(v4 + 9098)
    && (unsigned int)WWWServerTraceProvider::CheckTracingEnabled((v4 + 8) & -(__int64)(v4 != 0), 0, 5) )
  {
    IISGeneralEvents::GENERAL_SET_REQUEST_HEADER::RaiseEvent(
      (struct IHttpTraceContext *)((*((_QWORD *)this + 14) + 8LL) & -(__int64)(*((_QWORD *)this + 14) != 0)),
      (const struct _GUID *)(*((_QWORD *)this + 14) + 8LL),
      a2,
      dword_1800395E4,
      1);
  }
  Key = STATIC_STRING_HASH<137>::FindKey(v4, a2);
  if ( Key && *(_DWORD *)(Key + 24) <= 0x28u )
  {
    v8 = *(unsigned int *)(Key + 24);
    *(_QWORD *)(*((_QWORD *)this + 5) + 16 * (v8 + 10)) = 0;
    *(_WORD *)(*((_QWORD *)this + 5) + 16 * v8 + 152) = 0;
  }
  else
  {
    v6 = *((_QWORD *)this + 5);
    if ( *(_WORD *)(v6 + 120) )
    {
      v9 = 0;
      do
      {
        if ( !_stricmp(*(const char **)(*(_QWORD *)(v6 + 128) + 24 * v9 + 8), a2) )
        {
          memmove_0(
            (void *)(*(_QWORD *)(*((_QWORD *)this + 5) + 128LL) + 24 * v9),
            (const void *)(*(_QWORD *)(*((_QWORD *)this + 5) + 128LL) + 24 * v9 + 24),
            24LL * (*(unsigned __int16 *)(*((_QWORD *)this + 5) + 120LL) - (unsigned int)v9 - 1));
          --*(_WORD *)(*((_QWORD *)this + 5) + 120LL);
        }
        else
        {
          v9 = (unsigned int)(v9 + 1);
        }
        v6 = *((_QWORD *)this + 5);
      }
      while ( (unsigned int)v9 < *(unsigned __int16 *)(v6 + 120) );
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180010444  push    rbx
0x180010446  push    rbp
0x180010447  push    rsi
0x180010448  push    rdi
0x180010449  sub     rsp, 38h
0x18001044d  mov     rsi, rdx
0x180010450  mov     rbx, rcx
0x180010453  test    rdx, rdx
0x180010456  jz      short loc_1800104BF
0x180010458  inc     dword ptr [rcx+30h]
0x18001045b  mov     rcx, [rcx+70h]
0x18001045f  cmp     byte ptr [rcx+238Ah], 0
0x180010466  jnz     short loc_1800104C6
0x180010468  mov     rdx, rsi
0x18001046b  call    ?FindKey@?$STATIC_STRING_HASH@$0IJ@@@QEAAPEAUSTATIC_STRING_HASH_RECORD@@PEBD@Z; STATIC_STRING_HASH<137>::FindKey(char const *)
0x180010470  test    rax, rax
0x180010473  jnz     short loc_180010490
0x180010475  mov     rcx, [rbx+28h]
0x180010479  xor     eax, eax
0x18001047b  cmp     ax, [rcx+78h]
0x18001047f  jb      loc_18001050F
0x180010485  xor     eax, eax
0x180010487  add     rsp, 38h
0x18001048b  pop     rdi
0x18001048c  pop     rsi
0x18001048d  pop     rbp
0x18001048e  pop     rbx
0x18001048f  retn
0x180010490  cmp     dword ptr [rax+18h], 28h ; '('
0x180010494  ja      short loc_180010475
0x180010496  mov     edx, [rax+18h]
0x180010499  mov     rax, [rbx+28h]
0x18001049d  lea     rcx, [rdx+0Ah]
0x1800104a1  add     rdx, rdx
0x1800104a4  add     rcx, rcx
0x1800104a7  mov     qword ptr [rax+rcx*8], 0
0x1800104af  xor     eax, eax
0x1800104b1  mov     rcx, [rbx+28h]
0x1800104b5  mov     [rcx+rdx*8+98h], ax
0x1800104bd  jmp     short loc_180010485
0x1800104bf  mov     eax, 80070057h
0x1800104c4  jmp     short loc_180010487
0x1800104c6  lea     rax, [rcx+8]
0x1800104ca  neg     rcx
0x1800104cd  sbb     rcx, rcx
0x1800104d0  xor     edx, edx
0x1800104d2  and     rcx, rax
0x1800104d5  lea     r8d, [rdx+5]
0x1800104d9  call    ?CheckTracingEnabled@WWWServerTraceProvider@@SAHPEAVIHttpTraceContext@@W4enumAreaFlags@1@K@Z; WWWServerTraceProvider::CheckTracingEnabled(IHttpTraceContext *,WWWServerTraceProvider::enumAreaFlags,ulong)
0x1800104de  test    eax, eax
0x1800104e0  jz      short loc_180010468
0x1800104e2  mov     rax, [rbx+70h]
0x1800104e6  lea     r9, dword_1800395E4; char *
0x1800104ed  mov     r8, rsi; char *
0x1800104f0  mov     dword ptr [rsp+58h+var_38], 1; char
0x1800104f8  lea     rdx, [rax+8]; struct _GUID *
0x1800104fc  neg     rax
0x1800104ff  sbb     rcx, rcx
0x180010502  and     rcx, rdx; struct IHttpTraceContext *
0x180010505  call    ?RaiseEvent@GENERAL_SET_REQUEST_HEADER@IISGeneralEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@PEBD2H@Z; IISGeneralEvents::GENERAL_SET_REQUEST_HEADER::RaiseEvent(IHttpTraceContext *,_GUID const *,char const *,char const *,int)
0x18001050a  jmp     loc_180010468
0x18001050f  xor     edi, edi
0x180010511  mov     rcx, [rcx+80h]
0x180010518  lea     rbp, [rdi+rdi*2]
0x18001051c  mov     rdx, rsi; String2
0x18001051f  mov     rcx, [rcx+rbp*8+8]; String1
0x180010524  call    cs:__imp__stricmp
0x18001052a  test    eax, eax
0x18001052c  jnz     short loc_180010565
0x18001052e  mov     rdx, [rbx+28h]
0x180010532  mov     rax, [rdx+80h]
0x180010539  lea     rcx, [rax+rbp*8]; void *
0x18001053d  movzx   eax, word ptr [rdx+78h]
0x180010541  sub     eax, edi
0x180010543  lea     rdx, [rcx+18h]; Src
0x180010547  dec     eax
0x180010549  lea     r8, [rax+rax*2]
0x18001054d  shl     r8, 3; Size
0x180010551  call    memmove_0
0x180010556  mov     rax, [rbx+28h]
0x18001055a  mov     ecx, 0FFFFh
0x18001055f  add     [rax+78h], cx
0x180010563  jmp     short loc_180010567
0x180010565  inc     edi
0x180010567  mov     rcx, [rbx+28h]
0x18001056b  movzx   eax, word ptr [rcx+78h]
0x18001056f  cmp     edi, eax
0x180010571  jb      short loc_180010511
0x180010573  jmp     loc_180010485
```
