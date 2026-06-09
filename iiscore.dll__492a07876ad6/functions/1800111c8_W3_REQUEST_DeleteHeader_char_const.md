# W3_REQUEST::DeleteHeader(char const *)

- ea: `0x1800111c8`
- end: `0x180011303`
- name: `?DeleteHeader@W3_REQUEST@@QEAAJPEBD@Z`
- size: `315`
- prototype: `int(W3_REQUEST *__hidden this, const char *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180024710`
- `0x18002910c`

## callees

- `0x180009030`
- `0x1800111c8`
- `0x180011460`
- `0x18002a000`
- `0x18003772e`

## import_xrefs

- `msvcrt!_stricmp` at `0x1800112a9`
- `msvcrt!_stricmp` at `0x1800112a9`

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
      dword_18003C5E4,
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
0x1800111c8  push    rbx
0x1800111ca  push    rbp
0x1800111cb  push    rsi
0x1800111cc  push    rdi
0x1800111cd  sub     rsp, 38h
0x1800111d1  mov     rsi, rdx
0x1800111d4  mov     rbx, rcx
0x1800111d7  test    rdx, rdx
0x1800111da  jz      short loc_180011244
0x1800111dc  inc     dword ptr [rcx+30h]
0x1800111df  mov     rcx, [rcx+70h]
0x1800111e3  cmp     byte ptr [rcx+238Ah], 0
0x1800111ea  jnz     short loc_18001124B
0x1800111ec  mov     rdx, rsi
0x1800111ef  call    ?FindKey@?$STATIC_STRING_HASH@$0IJ@@@QEAAPEAUSTATIC_STRING_HASH_RECORD@@PEBD@Z; STATIC_STRING_HASH<137>::FindKey(char const *)
0x1800111f4  test    rax, rax
0x1800111f7  jnz     short loc_180011215
0x1800111f9  mov     rcx, [rbx+28h]
0x1800111fd  xor     eax, eax
0x1800111ff  cmp     ax, [rcx+78h]
0x180011203  jb      loc_180011294
0x180011209  xor     eax, eax
0x18001120b  add     rsp, 38h
0x18001120f  pop     rdi
0x180011210  pop     rsi
0x180011211  pop     rbp
0x180011212  pop     rbx
0x180011213  retn
0x180011215  cmp     dword ptr [rax+18h], 28h ; '('
0x180011219  ja      short loc_1800111F9
0x18001121b  mov     edx, [rax+18h]
0x18001121e  mov     rax, [rbx+28h]
0x180011222  lea     rcx, [rdx+0Ah]
0x180011226  add     rdx, rdx
0x180011229  add     rcx, rcx
0x18001122c  mov     qword ptr [rax+rcx*8], 0
0x180011234  xor     eax, eax
0x180011236  mov     rcx, [rbx+28h]
0x18001123a  mov     [rcx+rdx*8+98h], ax
0x180011242  jmp     short loc_180011209
0x180011244  mov     eax, 80070057h
0x180011249  jmp     short loc_18001120B
0x18001124b  lea     rax, [rcx+8]
0x18001124f  neg     rcx
0x180011252  sbb     rcx, rcx
0x180011255  xor     edx, edx
0x180011257  and     rcx, rax
0x18001125a  lea     r8d, [rdx+5]
0x18001125e  call    ?CheckTracingEnabled@WWWServerTraceProvider@@SAHPEAVIHttpTraceContext@@W4enumAreaFlags@1@K@Z; WWWServerTraceProvider::CheckTracingEnabled(IHttpTraceContext *,WWWServerTraceProvider::enumAreaFlags,ulong)
0x180011263  test    eax, eax
0x180011265  jz      short loc_1800111EC
0x180011267  mov     rax, [rbx+70h]
0x18001126b  lea     r9, dword_18003C5E4; char *
0x180011272  mov     r8, rsi; char *
0x180011275  mov     dword ptr [rsp+58h+var_38], 1; char
0x18001127d  lea     rdx, [rax+8]; struct _GUID *
0x180011281  neg     rax
0x180011284  sbb     rcx, rcx
0x180011287  and     rcx, rdx; struct IHttpTraceContext *
0x18001128a  call    ?RaiseEvent@GENERAL_SET_REQUEST_HEADER@IISGeneralEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@PEBD2H@Z; IISGeneralEvents::GENERAL_SET_REQUEST_HEADER::RaiseEvent(IHttpTraceContext *,_GUID const *,char const *,char const *,int)
0x18001128f  jmp     loc_1800111EC
0x180011294  xor     edi, edi
0x180011296  mov     rcx, [rcx+80h]
0x18001129d  lea     rbp, [rdi+rdi*2]
0x1800112a1  mov     rdx, rsi; String2
0x1800112a4  mov     rcx, [rcx+rbp*8+8]; String1
0x1800112a9  call    cs:__imp__stricmp
0x1800112b0  nop     dword ptr [rax+rax+00h]
0x1800112b5  test    eax, eax
0x1800112b7  jnz     short loc_1800112F0
0x1800112b9  mov     rdx, [rbx+28h]
0x1800112bd  mov     rax, [rdx+80h]
0x1800112c4  lea     rcx, [rax+rbp*8]; void *
0x1800112c8  movzx   eax, word ptr [rdx+78h]
0x1800112cc  sub     eax, edi
0x1800112ce  lea     rdx, [rcx+18h]; Src
0x1800112d2  dec     eax
0x1800112d4  lea     r8, [rax+rax*2]
0x1800112d8  shl     r8, 3; Size
0x1800112dc  call    memmove_0
0x1800112e1  mov     rax, [rbx+28h]
0x1800112e5  mov     ecx, 0FFFFh
0x1800112ea  add     [rax+78h], cx
0x1800112ee  jmp     short loc_1800112F2
0x1800112f0  inc     edi
0x1800112f2  mov     rcx, [rbx+28h]
0x1800112f6  movzx   eax, word ptr [rcx+78h]
0x1800112fa  cmp     edi, eax
0x1800112fc  jb      short loc_180011296
0x1800112fe  jmp     loc_180011209
```
