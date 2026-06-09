# REQUEST_CONTEXT::DeleteHeader(char const *)

- ea: `0x180011310`
- end: `0x18001144c`
- name: `?DeleteHeader@REQUEST_CONTEXT@@UEAAJPEBD@Z`
- size: `316`
- prototype: `int(REQUEST_CONTEXT *__hidden this, const char *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180009030`
- `0x180011310`
- `0x180011460`
- `0x18002a000`
- `0x18003772e`

## import_xrefs

- `msvcrt!_stricmp` at `0x1800113f2`
- `msvcrt!_stricmp` at `0x1800113f2`

## pseudocode

```c
__int64 __fastcall REQUEST_CONTEXT::DeleteHeader(REQUEST_CONTEXT *this, const char *a2)
{
  __int64 v3; // rbx
  __int64 v4; // rcx
  __int64 Key; // rax
  __int64 v6; // rcx
  __int64 v8; // rdx
  __int64 v9; // rdi

  if ( !a2 )
    return 2147942487LL;
  v3 = *((_QWORD *)this + 1);
  v4 = *(_QWORD *)(v3 + 112);
  ++*(_DWORD *)(v3 + 48);
  if ( *(_BYTE *)(v4 + 9098)
    && (unsigned int)WWWServerTraceProvider::CheckTracingEnabled((v4 + 8) & -(__int64)(v4 != 0), 0, 5) )
  {
    IISGeneralEvents::GENERAL_SET_REQUEST_HEADER::RaiseEvent(
      (struct IHttpTraceContext *)((*(_QWORD *)(v3 + 112) + 8LL) & -(__int64)(*(_QWORD *)(v3 + 112) != 0)),
      (const struct _GUID *)(*(_QWORD *)(v3 + 112) + 8LL),
      a2,
      dword_18003C5E4,
      1);
  }
  Key = STATIC_STRING_HASH<137>::FindKey(v4, a2);
  if ( Key && *(_DWORD *)(Key + 24) <= 0x28u )
  {
    v8 = *(unsigned int *)(Key + 24);
    *(_QWORD *)(*(_QWORD *)(v3 + 40) + 16 * (v8 + 10)) = 0;
    *(_WORD *)(*(_QWORD *)(v3 + 40) + 16 * v8 + 152) = 0;
  }
  else
  {
    v6 = *(_QWORD *)(v3 + 40);
    if ( *(_WORD *)(v6 + 120) )
    {
      v9 = 0;
      do
      {
        if ( !_stricmp(*(const char **)(*(_QWORD *)(v6 + 128) + 24 * v9 + 8), a2) )
        {
          memmove_0(
            (void *)(*(_QWORD *)(*(_QWORD *)(v3 + 40) + 128LL) + 24 * v9),
            (const void *)(*(_QWORD *)(*(_QWORD *)(v3 + 40) + 128LL) + 24 * v9 + 24),
            24LL * (*(unsigned __int16 *)(*(_QWORD *)(v3 + 40) + 120LL) - (unsigned int)v9 - 1));
          --*(_WORD *)(*(_QWORD *)(v3 + 40) + 120LL);
        }
        else
        {
          v9 = (unsigned int)(v9 + 1);
        }
        v6 = *(_QWORD *)(v3 + 40);
      }
      while ( (unsigned int)v9 < *(unsigned __int16 *)(v6 + 120) );
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180011310  push    rbx
0x180011312  push    rbp
0x180011313  push    rsi
0x180011314  push    rdi
0x180011315  sub     rsp, 38h
0x180011319  mov     rsi, rdx
0x18001131c  test    rdx, rdx
0x18001131f  jz      short loc_18001138D
0x180011321  mov     rbx, [rcx+8]
0x180011325  mov     rcx, [rbx+70h]
0x180011329  inc     dword ptr [rbx+30h]
0x18001132c  cmp     byte ptr [rcx+238Ah], 0
0x180011333  jnz     short loc_180011394
0x180011335  mov     rdx, rsi
0x180011338  call    ?FindKey@?$STATIC_STRING_HASH@$0IJ@@@QEAAPEAUSTATIC_STRING_HASH_RECORD@@PEBD@Z; STATIC_STRING_HASH<137>::FindKey(char const *)
0x18001133d  test    rax, rax
0x180011340  jnz     short loc_18001135E
0x180011342  mov     rcx, [rbx+28h]
0x180011346  xor     eax, eax
0x180011348  cmp     ax, [rcx+78h]
0x18001134c  jb      loc_1800113DD
0x180011352  xor     eax, eax
0x180011354  add     rsp, 38h
0x180011358  pop     rdi
0x180011359  pop     rsi
0x18001135a  pop     rbp
0x18001135b  pop     rbx
0x18001135c  retn
0x18001135e  cmp     dword ptr [rax+18h], 28h ; '('
0x180011362  ja      short loc_180011342
0x180011364  mov     edx, [rax+18h]
0x180011367  mov     rax, [rbx+28h]
0x18001136b  lea     rcx, [rdx+0Ah]
0x18001136f  add     rdx, rdx
0x180011372  add     rcx, rcx
0x180011375  mov     qword ptr [rax+rcx*8], 0
0x18001137d  xor     eax, eax
0x18001137f  mov     rcx, [rbx+28h]
0x180011383  mov     [rcx+rdx*8+98h], ax
0x18001138b  jmp     short loc_180011352
0x18001138d  mov     eax, 80070057h
0x180011392  jmp     short loc_180011354
0x180011394  lea     rax, [rcx+8]
0x180011398  neg     rcx
0x18001139b  sbb     rcx, rcx
0x18001139e  xor     edx, edx
0x1800113a0  and     rcx, rax
0x1800113a3  lea     r8d, [rdx+5]
0x1800113a7  call    ?CheckTracingEnabled@WWWServerTraceProvider@@SAHPEAVIHttpTraceContext@@W4enumAreaFlags@1@K@Z; WWWServerTraceProvider::CheckTracingEnabled(IHttpTraceContext *,WWWServerTraceProvider::enumAreaFlags,ulong)
0x1800113ac  test    eax, eax
0x1800113ae  jz      short loc_180011335
0x1800113b0  mov     rax, [rbx+70h]
0x1800113b4  lea     r9, dword_18003C5E4; char *
0x1800113bb  mov     r8, rsi; char *
0x1800113be  mov     dword ptr [rsp+58h+var_38], 1; char
0x1800113c6  lea     rdx, [rax+8]; struct _GUID *
0x1800113ca  neg     rax
0x1800113cd  sbb     rcx, rcx
0x1800113d0  and     rcx, rdx; struct IHttpTraceContext *
0x1800113d3  call    ?RaiseEvent@GENERAL_SET_REQUEST_HEADER@IISGeneralEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@PEBD2H@Z; IISGeneralEvents::GENERAL_SET_REQUEST_HEADER::RaiseEvent(IHttpTraceContext *,_GUID const *,char const *,char const *,int)
0x1800113d8  jmp     loc_180011335
0x1800113dd  xor     edi, edi
0x1800113df  mov     rcx, [rcx+80h]
0x1800113e6  lea     rbp, [rdi+rdi*2]
0x1800113ea  mov     rdx, rsi; String2
0x1800113ed  mov     rcx, [rcx+rbp*8+8]; String1
0x1800113f2  call    cs:__imp__stricmp
0x1800113f9  nop     dword ptr [rax+rax+00h]
0x1800113fe  test    eax, eax
0x180011400  jnz     short loc_180011439
0x180011402  mov     rdx, [rbx+28h]
0x180011406  mov     rax, [rdx+80h]
0x18001140d  lea     rcx, [rax+rbp*8]; void *
0x180011411  movzx   eax, word ptr [rdx+78h]
0x180011415  sub     eax, edi
0x180011417  lea     rdx, [rcx+18h]; Src
0x18001141b  dec     eax
0x18001141d  lea     r8, [rax+rax*2]
0x180011421  shl     r8, 3; Size
0x180011425  call    memmove_0
0x18001142a  mov     rax, [rbx+28h]
0x18001142e  mov     ecx, 0FFFFh
0x180011433  add     [rax+78h], cx
0x180011437  jmp     short loc_18001143B
0x180011439  inc     edi
0x18001143b  mov     rcx, [rbx+28h]
0x18001143f  movzx   eax, word ptr [rcx+78h]
0x180011443  cmp     edi, eax
0x180011445  jb      short loc_1800113DF
0x180011447  jmp     loc_180011352
```
