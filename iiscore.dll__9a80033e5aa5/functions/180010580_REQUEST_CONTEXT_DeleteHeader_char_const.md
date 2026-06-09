# REQUEST_CONTEXT::DeleteHeader(char const *)

- ea: `0x180010580`
- end: `0x1800106b5`
- name: `?DeleteHeader@REQUEST_CONTEXT@@UEAAJPEBD@Z`
- size: `309`
- prototype: `int(REQUEST_CONTEXT *__hidden this, const char *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180008930`
- `0x180010580`
- `0x1800106c0`
- `0x180027e10`
- `0x18003438e`

## import_xrefs

- `msvcrt!_stricmp` at `0x180010661`
- `msvcrt!_stricmp` at `0x180010661`

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
      dword_1800395E4,
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
0x180010580  push    rbx
0x180010582  push    rbp
0x180010583  push    rsi
0x180010584  push    rdi
0x180010585  sub     rsp, 38h
0x180010589  mov     rsi, rdx
0x18001058c  test    rdx, rdx
0x18001058f  jz      short loc_1800105FC
0x180010591  mov     rbx, [rcx+8]
0x180010595  mov     rcx, [rbx+70h]
0x180010599  inc     dword ptr [rbx+30h]
0x18001059c  cmp     byte ptr [rcx+238Ah], 0
0x1800105a3  jnz     short loc_180010603
0x1800105a5  mov     rdx, rsi
0x1800105a8  call    ?FindKey@?$STATIC_STRING_HASH@$0IJ@@@QEAAPEAUSTATIC_STRING_HASH_RECORD@@PEBD@Z; STATIC_STRING_HASH<137>::FindKey(char const *)
0x1800105ad  test    rax, rax
0x1800105b0  jnz     short loc_1800105CD
0x1800105b2  mov     rcx, [rbx+28h]
0x1800105b6  xor     eax, eax
0x1800105b8  cmp     ax, [rcx+78h]
0x1800105bc  jb      loc_18001064C
0x1800105c2  xor     eax, eax
0x1800105c4  add     rsp, 38h
0x1800105c8  pop     rdi
0x1800105c9  pop     rsi
0x1800105ca  pop     rbp
0x1800105cb  pop     rbx
0x1800105cc  retn
0x1800105cd  cmp     dword ptr [rax+18h], 28h ; '('
0x1800105d1  ja      short loc_1800105B2
0x1800105d3  mov     edx, [rax+18h]
0x1800105d6  mov     rax, [rbx+28h]
0x1800105da  lea     rcx, [rdx+0Ah]
0x1800105de  add     rdx, rdx
0x1800105e1  add     rcx, rcx
0x1800105e4  mov     qword ptr [rax+rcx*8], 0
0x1800105ec  xor     eax, eax
0x1800105ee  mov     rcx, [rbx+28h]
0x1800105f2  mov     [rcx+rdx*8+98h], ax
0x1800105fa  jmp     short loc_1800105C2
0x1800105fc  mov     eax, 80070057h
0x180010601  jmp     short loc_1800105C4
0x180010603  lea     rax, [rcx+8]
0x180010607  neg     rcx
0x18001060a  sbb     rcx, rcx
0x18001060d  xor     edx, edx
0x18001060f  and     rcx, rax
0x180010612  lea     r8d, [rdx+5]
0x180010616  call    ?CheckTracingEnabled@WWWServerTraceProvider@@SAHPEAVIHttpTraceContext@@W4enumAreaFlags@1@K@Z; WWWServerTraceProvider::CheckTracingEnabled(IHttpTraceContext *,WWWServerTraceProvider::enumAreaFlags,ulong)
0x18001061b  test    eax, eax
0x18001061d  jz      short loc_1800105A5
0x18001061f  mov     rax, [rbx+70h]
0x180010623  lea     r9, dword_1800395E4; char *
0x18001062a  mov     r8, rsi; char *
0x18001062d  mov     dword ptr [rsp+58h+var_38], 1; char
0x180010635  lea     rdx, [rax+8]; struct _GUID *
0x180010639  neg     rax
0x18001063c  sbb     rcx, rcx
0x18001063f  and     rcx, rdx; struct IHttpTraceContext *
0x180010642  call    ?RaiseEvent@GENERAL_SET_REQUEST_HEADER@IISGeneralEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@PEBD2H@Z; IISGeneralEvents::GENERAL_SET_REQUEST_HEADER::RaiseEvent(IHttpTraceContext *,_GUID const *,char const *,char const *,int)
0x180010647  jmp     loc_1800105A5
0x18001064c  xor     edi, edi
0x18001064e  mov     rcx, [rcx+80h]
0x180010655  lea     rbp, [rdi+rdi*2]
0x180010659  mov     rdx, rsi; String2
0x18001065c  mov     rcx, [rcx+rbp*8+8]; String1
0x180010661  call    cs:__imp__stricmp
0x180010667  test    eax, eax
0x180010669  jnz     short loc_1800106A2
0x18001066b  mov     rdx, [rbx+28h]
0x18001066f  mov     rax, [rdx+80h]
0x180010676  lea     rcx, [rax+rbp*8]; void *
0x18001067a  movzx   eax, word ptr [rdx+78h]
0x18001067e  sub     eax, edi
0x180010680  lea     rdx, [rcx+18h]; Src
0x180010684  dec     eax
0x180010686  lea     r8, [rax+rax*2]
0x18001068a  shl     r8, 3; Size
0x18001068e  call    memmove_0
0x180010693  mov     rax, [rbx+28h]
0x180010697  mov     ecx, 0FFFFh
0x18001069c  add     [rax+78h], cx
0x1800106a0  jmp     short loc_1800106A4
0x1800106a2  inc     edi
0x1800106a4  mov     rcx, [rbx+28h]
0x1800106a8  movzx   eax, word ptr [rcx+78h]
0x1800106ac  cmp     edi, eax
0x1800106ae  jb      short loc_18001064E
0x1800106b0  jmp     loc_1800105C2
```
