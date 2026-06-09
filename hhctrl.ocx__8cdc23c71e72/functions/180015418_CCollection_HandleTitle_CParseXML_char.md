# CCollection::HandleTitle(CParseXML *,char *)

- ea: `0x180015418`
- end: `0x180015896`
- name: `?HandleTitle@CCollection@@AEAAKPEAVCParseXML@@PEAD@Z`
- size: `1150`
- prototype: `unsigned int(CCollection *__hidden this, struct CParseXML *, char *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180015dc0`

## callees

- `0x180001710`
- `0x180014900`
- `0x18001499c`
- `0x180015418`
- `0x180015968`
- `0x1800159d0`
- `0x180047854`
- `0x1800478fc`
- `0x1800479dc`
- `0x180047a6c`
- `0x180047b7c`
- `0x180065438`

## import_xrefs

- `KERNEL32!lstrcmpiA` at `0x180015484`
- `KERNEL32!lstrcmpiA` at `0x1800154b5`
- `KERNEL32!lstrcmpiA` at `0x1800154d4`
- `KERNEL32!lstrcmpiA` at `0x180015528`
- `KERNEL32!lstrcmpiA` at `0x18001555d`
- `KERNEL32!lstrcmpiA` at `0x1800155b1`
- `KERNEL32!lstrcmpiA` at `0x18001561e`
- `KERNEL32!lstrcmpiA` at `0x180015691`
- `KERNEL32!lstrcmpiA` at `0x1800156cc`
- `KERNEL32!lstrcmpiA` at `0x1800156fe`
- `KERNEL32!lstrcmpiA` at `0x180015730`
- `KERNEL32!lstrcmpiA` at `0x180015765`
- `KERNEL32!lstrcmpiA` at `0x18001579a`
- `KERNEL32!lstrcmpiA` at `0x1800157e3`
- `KERNEL32!lstrcmpiA` at `0x18001582c`
- `KERNEL32!lstrcmpiA` at `0x180015484`
- `KERNEL32!lstrcmpiA` at `0x1800154b5`
- `KERNEL32!lstrcmpiA` at `0x1800154d4`
- `KERNEL32!lstrcmpiA` at `0x180015528`
- `KERNEL32!lstrcmpiA` at `0x18001555d`
- `KERNEL32!lstrcmpiA` at `0x1800155b1`
- `KERNEL32!lstrcmpiA` at `0x18001561e`
- `KERNEL32!lstrcmpiA` at `0x180015691`
- `KERNEL32!lstrcmpiA` at `0x1800156cc`
- `KERNEL32!lstrcmpiA` at `0x1800156fe`
- `KERNEL32!lstrcmpiA` at `0x180015730`
- `KERNEL32!lstrcmpiA` at `0x180015765`
- `KERNEL32!lstrcmpiA` at `0x18001579a`
- `KERNEL32!lstrcmpiA` at `0x1800157e3`
- `KERNEL32!lstrcmpiA` at `0x18001582c`

## string_xrefs

- `0x18001547d`: `DocCompId`
- `0x180015521`: `DocCompLanguage`

## pseudocode

```c
unsigned int __fastcall CCollection::HandleTitle(CCollection *this, struct CParseXML *a2, char *a3)
{
  char *v5; // rbp
  struct CTitle *v6; // rsi
  int v7; // r15d
  const char *Token; // rax
  char *v9; // rbx
  const CHAR *FirstWord; // rax
  const char *v11; // rax
  const CHAR *v12; // rax
  const CHAR *v13; // rax
  CCollection *v14; // rcx
  char **v15; // r9
  char *v16; // r8
  struct CParseXML *v17; // rdx
  unsigned int result; // eax
  const CHAR *v19; // rax
  const char *v20; // rax
  const CHAR *v21; // rax
  const char *v22; // rax
  const char *v23; // rax
  const CHAR *v24; // rax
  const char *v25; // rax
  const CHAR *v26; // rax
  char *v27; // rax
  __int64 v28; // rbx
  int v29; // r8d
  int v30; // edx
  const CHAR *v31; // rax
  __int64 v32; // r9
  const CHAR *v33; // rax
  __int64 v34; // r9
  const CHAR *v35; // rax
  __int64 v36; // r9
  const CHAR *v37; // rax
  __int64 v38; // r9
  const CHAR *v39; // rax
  __int64 v40; // r9
  const CHAR *v41; // rax
  const char *v42; // rax
  const CHAR *v43; // rax
  const char *v44; // rax
  const CHAR *v45; // rax
  const char *Value; // rax
  char *v47; // [rsp+58h] [rbp+10h] BYREF
  char *v48; // [rsp+68h] [rbp+20h] BYREF

  if ( !a2 || !a3 )
    return 11;
  v5 = 0;
  v6 = CCollection::NewTitle(this);
  v47 = 0;
  if ( !v6 )
    return 4;
  v7 = 0;
  while ( 1 )
  {
    Token = CParseXML::GetToken(a2);
    v9 = (char *)Token;
    if ( !Token )
      break;
    FirstWord = CParseXML::GetFirstWord(a2, Token);
    if ( lstrcmpiA(FirstWord, "DocCompId") )
    {
      v12 = CParseXML::GetFirstWord(a2, v9);
      if ( lstrcmpiA(v12, "TitleString") )
      {
        v13 = CParseXML::GetFirstWord(a2, v9);
        if ( lstrcmpiA(v13, "TitleSampleLocation") )
        {
          v19 = CParseXML::GetFirstWord(a2, v9);
          if ( lstrcmpiA(v19, "DocCompLanguage") )
          {
            v21 = CParseXML::GetFirstWord(a2, v9);
            if ( lstrcmpiA(v21, "SupportsMerge") )
            {
              v24 = CParseXML::GetFirstWord(a2, v9);
              if ( lstrcmpiA(v24, "LocationHistory") )
              {
                v26 = CParseXML::GetFirstWord(a2, v9);
                if ( lstrcmpiA(v26, "/LocationHistory") )
                {
                  v31 = CParseXML::GetFirstWord(a2, v9);
                  if ( !lstrcmpiA(v31, "TitleLocation") )
                  {
                    v32 = *((_QWORD *)v6 + 5);
                    if ( !v32 )
                      return 4;
                    v15 = (char **)(v32 + 8);
LABEL_36:
                    v16 = v9;
                    v17 = a2;
LABEL_12:
                    result = CCollection::AllocCopyValue(v14, v17, v16, v15);
                    goto LABEL_13;
                  }
                  v33 = CParseXML::GetFirstWord(a2, v9);
                  if ( !lstrcmpiA(v33, "QueryLocation") )
                  {
                    v34 = *((_QWORD *)v6 + 5);
                    if ( !v34 )
                      return 4;
                    v15 = (char **)(v34 + 24);
                    goto LABEL_36;
                  }
                  v35 = CParseXML::GetFirstWord(a2, v9);
                  if ( !lstrcmpiA(v35, "TitleQueryLocation") )
                  {
                    v36 = *((_QWORD *)v6 + 5);
                    if ( !v36 )
                      return 4;
                    v15 = (char **)(v36 + 64);
                    goto LABEL_36;
                  }
                  v37 = CParseXML::GetFirstWord(a2, v9);
                  if ( !lstrcmpiA(v37, "IndexLocation") )
                  {
                    v38 = *((_QWORD *)v6 + 5);
                    if ( !v38 )
                      return 4;
                    v15 = (char **)(v38 + 16);
                    goto LABEL_36;
                  }
                  v39 = CParseXML::GetFirstWord(a2, v9);
                  if ( !lstrcmpiA(v39, "LocationRef") )
                  {
                    v40 = *((_QWORD *)v6 + 5);
                    if ( !v40 )
                      return 4;
                    v15 = (char **)(v40 + 32);
                    goto LABEL_36;
                  }
                  v41 = CParseXML::GetFirstWord(a2, v9);
                  if ( lstrcmpiA(v41, "Version") )
                  {
                    v43 = CParseXML::GetFirstWord(a2, v9);
                    if ( lstrcmpiA(v43, "LastPromptedVersion") )
                    {
                      v45 = CParseXML::GetFirstWord(a2, v9);
                      if ( lstrcmpiA(v45, "ColNum") )
                        break;
                      if ( !*((_QWORD *)v6 + 5) )
                        return 4;
                      Value = CParseXML::GetValue(a2, v9);
                      *(_DWORD *)(*((_QWORD *)v6 + 5) + 40LL) = Atoi(Value);
                    }
                    else
                    {
                      if ( !*((_QWORD *)v6 + 5) )
                        return 4;
                      v44 = CParseXML::GetValue(a2, v9);
                      *(_DWORD *)(*((_QWORD *)v6 + 5) + 48LL) = Atoi(v44);
                    }
                  }
                  else
                  {
                    if ( !*((_QWORD *)v6 + 5) )
                      return 4;
                    v42 = CParseXML::GetValue(a2, v9);
                    *(_DWORD *)(*((_QWORD *)v6 + 5) + 44LL) = Atoi(v42);
                  }
                }
                else
                {
                  v48 = 0;
                  result = CFIFOString::GetTail((CCollection *)((char *)this + 112), &v48);
                  if ( result )
                    return result;
                  v27 = v48;
                  v28 = v9 + 1 - v48;
                  do
                  {
                    v29 = (unsigned __int8)v27[v28];
                    v30 = (unsigned __int8)*v27 - v29;
                    if ( v30 )
                      break;
                    ++v27;
                  }
                  while ( v29 );
                  if ( v30 )
                  {
                    operator delete[](v48);
                    return 7;
                  }
                  operator delete[](v48);
                }
              }
              else
              {
                if ( !CTitle::NewLocationHistory(v6) )
                  return 4;
                if ( v5 )
                {
                  result = AllocSetValue(v5, *((char ***)v6 + 5));
                  if ( result )
                    return result;
                }
                *(_DWORD *)(*((_QWORD *)v6 + 5) + 52LL) = v7;
                v25 = CParseXML::GetFirstWord(a2, v9);
                result = CFIFOString::AddTail((CCollection *)((char *)this + 112), v25);
LABEL_13:
                if ( result )
                  return result;
              }
            }
            else if ( *((_QWORD *)v6 + 5) )
            {
              v23 = CParseXML::GetValue(a2, v9);
              *(_DWORD *)(*((_QWORD *)v6 + 5) + 52LL) = Atoi(v23);
            }
            else
            {
              v22 = CParseXML::GetValue(a2, v9);
              v7 = Atoi(v22);
            }
          }
          else
          {
            v20 = CParseXML::GetValue(a2, v9);
            *((_WORD *)v6 + 8) = Atoi(v20);
          }
        }
        else
        {
          v15 = (char **)*((_QWORD *)v6 + 5);
          v16 = v9;
          v17 = a2;
          if ( v15 )
            goto LABEL_12;
          CCollection::AllocCopyValue(v14, a2, v9, &v47);
          v5 = v47;
        }
      }
    }
    else
    {
      v11 = CParseXML::GetValue(a2, v9);
      AllocSetValue(v11, (char **)v6);
    }
  }
  if ( v5 )
    operator delete[](v5);
  return 0;
}

```

## disassembly

```asm
0x180015418  mov     [rsp+arg_0], rbx
0x18001541d  push    rbp
0x18001541e  push    rsi
0x18001541f  push    rdi
0x180015420  push    r14
0x180015422  push    r15
0x180015424  sub     rsp, 20h
0x180015428  mov     rdi, rdx
0x18001542b  mov     r14, rcx
0x18001542e  test    rdx, rdx
0x180015431  jz      loc_180015880
0x180015437  test    r8, r8
0x18001543a  jz      loc_180015880
0x180015440  call    ?NewTitle@CCollection@@AEAAPEAVCTitle@@XZ; CCollection::NewTitle(void)
0x180015445  xor     ebp, ebp
0x180015447  mov     rsi, rax
0x18001544a  mov     [rsp+48h+arg_8], rbp
0x18001544f  test    rax, rax
0x180015452  jz      loc_180015879
0x180015458  xor     r15d, r15d
0x18001545b  mov     rcx, rdi; this
0x18001545e  call    ?GetToken@CParseXML@@QEAAPEADXZ; CParseXML::GetToken(void)
0x180015463  mov     rbx, rax
0x180015466  test    rax, rax
0x180015469  jz      loc_180015868
0x18001546f  mov     rdx, rax; char *
0x180015472  mov     rcx, rdi; this
0x180015475  call    ?GetFirstWord@CParseXML@@QEAAPEADPEBD@Z; CParseXML::GetFirstWord(char const *)
0x18001547a  mov     rcx, rax; lpString1
0x18001547d  lea     rdx, aDoccompid; "DocCompId"
0x180015484  call    cs:__imp_lstrcmpiA
0x18001548a  mov     rdx, rbx; char *
0x18001548d  mov     rcx, rdi; this
0x180015490  test    eax, eax
0x180015492  jnz     short loc_1800154A6
0x180015494  call    ?GetValue@CParseXML@@QEAAPEADPEBD@Z; CParseXML::GetValue(char const *)
0x180015499  mov     rdx, rsi; char **
0x18001549c  mov     rcx, rax; char *
0x18001549f  call    ?AllocSetValue@@YAKPEBDPEAPEAD@Z; AllocSetValue(char const *,char * *)
0x1800154a4  jmp     short loc_18001545B
0x1800154a6  call    ?GetFirstWord@CParseXML@@QEAAPEADPEBD@Z; CParseXML::GetFirstWord(char const *)
0x1800154ab  mov     rcx, rax; lpString1
0x1800154ae  lea     rdx, aTitlestring; "TitleString"
0x1800154b5  call    cs:__imp_lstrcmpiA
0x1800154bb  test    eax, eax
0x1800154bd  jz      short loc_18001545B
0x1800154bf  mov     rdx, rbx; char *
0x1800154c2  mov     rcx, rdi; this
0x1800154c5  call    ?GetFirstWord@CParseXML@@QEAAPEADPEBD@Z; CParseXML::GetFirstWord(char const *)
0x1800154ca  mov     rcx, rax; lpString1
0x1800154cd  lea     rdx, aTitlesampleloc; "TitleSampleLocation"
0x1800154d4  call    cs:__imp_lstrcmpiA
0x1800154da  test    eax, eax
0x1800154dc  jnz     short loc_180015513
0x1800154de  mov     r9, [rsi+28h]; char **
0x1800154e2  mov     r8, rbx; char *
0x1800154e5  mov     rdx, rdi; struct CParseXML *
0x1800154e8  test    r9, r9
0x1800154eb  jnz     short loc_180015501
0x1800154ed  lea     r9, [rsp+48h+arg_8]; char **
0x1800154f2  call    ?AllocCopyValue@CCollection@@AEAAKPEAVCParseXML@@PEADPEAPEAD@Z; CCollection::AllocCopyValue(CParseXML *,char *,char * *)
0x1800154f7  mov     rbp, [rsp+48h+arg_8]
0x1800154fc  jmp     loc_18001545B
0x180015501  call    ?AllocCopyValue@CCollection@@AEAAKPEAVCParseXML@@PEADPEAPEAD@Z; CCollection::AllocCopyValue(CParseXML *,char *,char * *)
0x180015506  test    eax, eax
0x180015508  jz      loc_18001545B
0x18001550e  jmp     loc_180015885
0x180015513  mov     rdx, rbx; char *
0x180015516  mov     rcx, rdi; this
0x180015519  call    ?GetFirstWord@CParseXML@@QEAAPEADPEBD@Z; CParseXML::GetFirstWord(char const *)
0x18001551e  mov     rcx, rax; lpString1
0x180015521  lea     rdx, aDoccomplanguag; "DocCompLanguage"
0x180015528  call    cs:__imp_lstrcmpiA
0x18001552e  mov     rdx, rbx; char *
0x180015531  mov     rcx, rdi; this
0x180015534  test    eax, eax
0x180015536  jnz     short loc_18001554E
0x180015538  call    ?GetValue@CParseXML@@QEAAPEADPEBD@Z; CParseXML::GetValue(char const *)
0x18001553d  mov     rcx, rax; char *
0x180015540  call    ?Atoi@@YAHPEBD@Z; Atoi(char const *)
0x180015545  mov     [rsi+10h], ax
0x180015549  jmp     loc_18001545B
0x18001554e  call    ?GetFirstWord@CParseXML@@QEAAPEADPEBD@Z; CParseXML::GetFirstWord(char const *)
0x180015553  mov     rcx, rax; lpString1
0x180015556  lea     rdx, aSupportsmerge; "SupportsMerge"
0x18001555d  call    cs:__imp_lstrcmpiA
0x180015563  mov     rdx, rbx; char *
0x180015566  mov     rcx, rdi; this
0x180015569  test    eax, eax
0x18001556b  jnz     short loc_1800155A2
0x18001556d  cmp     qword ptr [rsi+28h], 0
0x180015572  jnz     short loc_180015589
0x180015574  call    ?GetValue@CParseXML@@QEAAPEADPEBD@Z; CParseXML::GetValue(char const *)
0x180015579  mov     rcx, rax; char *
0x18001557c  call    ?Atoi@@YAHPEBD@Z; Atoi(char const *)
0x180015581  mov     r15d, eax
0x180015584  jmp     loc_18001545B
0x180015589  call    ?GetValue@CParseXML@@QEAAPEADPEBD@Z; CParseXML::GetValue(char const *)
0x18001558e  mov     rcx, rax; char *
0x180015591  call    ?Atoi@@YAHPEBD@Z; Atoi(char const *)
0x180015596  mov     rcx, [rsi+28h]
0x18001559a  mov     [rcx+34h], eax
0x18001559d  jmp     loc_18001545B
0x1800155a2  call    ?GetFirstWord@CParseXML@@QEAAPEADPEBD@Z; CParseXML::GetFirstWord(char const *)
0x1800155a7  mov     rcx, rax; lpString1
0x1800155aa  lea     rdx, aLocationhistor_2; "LocationHistory"
0x1800155b1  call    cs:__imp_lstrcmpiA
0x1800155b7  test    eax, eax
0x1800155b9  jnz     short loc_180015609
0x1800155bb  mov     rcx, rsi; this
0x1800155be  call    ?NewLocationHistory@CTitle@@QEAAPEAULocationHistory@@XZ; CTitle::NewLocationHistory(void)
0x1800155c3  test    rax, rax
0x1800155c6  jz      loc_180015879
0x1800155cc  test    rbp, rbp
0x1800155cf  jz      short loc_1800155E5
0x1800155d1  mov     rdx, [rsi+28h]; char **
0x1800155d5  mov     rcx, rbp; char *
0x1800155d8  call    ?AllocSetValue@@YAKPEBDPEAPEAD@Z; AllocSetValue(char const *,char * *)
0x1800155dd  test    eax, eax
0x1800155df  jnz     loc_180015885
0x1800155e5  mov     rax, [rsi+28h]
0x1800155e9  mov     rdx, rbx; char *
0x1800155ec  mov     rcx, rdi; this
0x1800155ef  mov     [rax+34h], r15d
0x1800155f3  call    ?GetFirstWord@CParseXML@@QEAAPEADPEBD@Z; CParseXML::GetFirstWord(char const *)
0x1800155f8  mov     rdx, rax; char *
0x1800155fb  lea     rcx, [r14+70h]; this
0x1800155ff  call    ?AddTail@CFIFOString@@QEAAKPEBD@Z; CFIFOString::AddTail(char const *)
0x180015604  jmp     loc_180015506
0x180015609  mov     rdx, rbx; char *
0x18001560c  mov     rcx, rdi; this
0x18001560f  call    ?GetFirstWord@CParseXML@@QEAAPEADPEBD@Z; CParseXML::GetFirstWord(char const *)
0x180015614  mov     rcx, rax; lpString1
0x180015617  lea     rdx, aLocationhistor; "/LocationHistory"
0x18001561e  call    cs:__imp_lstrcmpiA
0x180015624  test    eax, eax
0x180015626  jnz     short loc_18001567C
0x180015628  lea     rcx, [r14+70h]; this
0x18001562c  mov     [rsp+48h+arg_18], 0
0x180015635  lea     rdx, [rsp+48h+arg_18]; char **
0x18001563a  call    ?GetTail@CFIFOString@@QEAAKPEAPEAD@Z; CFIFOString::GetTail(char * *)
0x18001563f  test    eax, eax
0x180015641  jnz     loc_180015885
0x180015647  mov     rcx, [rsp+48h+arg_18]; void *
0x18001564c  inc     rbx
0x18001564f  mov     rax, rcx
0x180015652  sub     rbx, rcx
0x180015655  movzx   edx, byte ptr [rax]
0x180015658  movzx   r8d, byte ptr [rax+rbx]
0x18001565d  sub     edx, r8d
0x180015660  jnz     short loc_18001566A
0x180015662  inc     rax
0x180015665  test    r8d, r8d
0x180015668  jnz     short loc_180015655
0x18001566a  test    edx, edx
0x18001566c  jnz     loc_18001585C
0x180015672  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180015677  jmp     loc_18001545B
0x18001567c  mov     rdx, rbx; char *
0x18001567f  mov     rcx, rdi; this
0x180015682  call    ?GetFirstWord@CParseXML@@QEAAPEADPEBD@Z; CParseXML::GetFirstWord(char const *)
0x180015687  mov     rcx, rax; lpString1
0x18001568a  lea     rdx, aTitlelocation; "TitleLocation"
0x180015691  call    cs:__imp_lstrcmpiA
0x180015697  test    eax, eax
0x180015699  jnz     short loc_1800156B7
0x18001569b  mov     r9, [rsi+28h]
0x18001569f  test    r9, r9
0x1800156a2  jz      loc_180015879
0x1800156a8  add     r9, 8
0x1800156ac  mov     r8, rbx
0x1800156af  mov     rdx, rdi
0x1800156b2  jmp     loc_180015501
0x1800156b7  mov     rdx, rbx; char *
0x1800156ba  mov     rcx, rdi; this
0x1800156bd  call    ?GetFirstWord@CParseXML@@QEAAPEADPEBD@Z; CParseXML::GetFirstWord(char const *)
0x1800156c2  mov     rcx, rax; lpString1
0x1800156c5  lea     rdx, aQuerylocation; "QueryLocation"
0x1800156cc  call    cs:__imp_lstrcmpiA
0x1800156d2  test    eax, eax
0x1800156d4  jnz     short loc_1800156E9
0x1800156d6  mov     r9, [rsi+28h]
0x1800156da  test    r9, r9
0x1800156dd  jz      loc_180015879
0x1800156e3  add     r9, 18h
0x1800156e7  jmp     short loc_1800156AC
0x1800156e9  mov     rdx, rbx; char *
0x1800156ec  mov     rcx, rdi; this
0x1800156ef  call    ?GetFirstWord@CParseXML@@QEAAPEADPEBD@Z; CParseXML::GetFirstWord(char const *)
0x1800156f4  mov     rcx, rax; lpString1
0x1800156f7  lea     rdx, aTitlequeryloca_0; "TitleQueryLocation"
0x1800156fe  call    cs:__imp_lstrcmpiA
0x180015704  test    eax, eax
0x180015706  jnz     short loc_18001571B
0x180015708  mov     r9, [rsi+28h]
0x18001570c  test    r9, r9
0x18001570f  jz      loc_180015879
0x180015715  add     r9, 40h ; '@'
0x180015719  jmp     short loc_1800156AC
0x18001571b  mov     rdx, rbx; char *
0x18001571e  mov     rcx, rdi; this
0x180015721  call    ?GetFirstWord@CParseXML@@QEAAPEADPEBD@Z; CParseXML::GetFirstWord(char const *)
0x180015726  mov     rcx, rax; lpString1
0x180015729  lea     rdx, aIndexlocation; "IndexLocation"
0x180015730  call    cs:__imp_lstrcmpiA
0x180015736  test    eax, eax
0x180015738  jnz     short loc_180015750
0x18001573a  mov     r9, [rsi+28h]
0x18001573e  test    r9, r9
0x180015741  jz      loc_180015879
0x180015747  add     r9, 10h
0x18001574b  jmp     loc_1800156AC
0x180015750  mov     rdx, rbx; char *
0x180015753  mov     rcx, rdi; this
0x180015756  call    ?GetFirstWord@CParseXML@@QEAAPEADPEBD@Z; CParseXML::GetFirstWord(char const *)
0x18001575b  mov     rcx, rax; lpString1
0x18001575e  lea     rdx, aLocationref; "LocationRef"
0x180015765  call    cs:__imp_lstrcmpiA
0x18001576b  test    eax, eax
0x18001576d  jnz     short loc_180015785
0x18001576f  mov     r9, [rsi+28h]
0x180015773  test    r9, r9
0x180015776  jz      loc_180015879
0x18001577c  add     r9, 20h ; ' '
0x180015780  jmp     loc_1800156AC
0x180015785  mov     rdx, rbx; char *
0x180015788  mov     rcx, rdi; this
0x18001578b  call    ?GetFirstWord@CParseXML@@QEAAPEADPEBD@Z; CParseXML::GetFirstWord(char const *)
0x180015790  mov     rcx, rax; lpString1
0x180015793  lea     rdx, aVersion; "Version"
0x18001579a  call    cs:__imp_lstrcmpiA
0x1800157a0  test    eax, eax
0x1800157a2  jnz     short loc_1800157CE
0x1800157a4  cmp     qword ptr [rsi+28h], 0
0x1800157a9  jz      loc_180015879
0x1800157af  mov     rdx, rbx; char *
0x1800157b2  mov     rcx, rdi; this
0x1800157b5  call    ?GetValue@CParseXML@@QEAAPEADPEBD@Z; CParseXML::GetValue(char const *)
0x1800157ba  mov     rcx, rax; char *
0x1800157bd  call    ?Atoi@@YAHPEBD@Z; Atoi(char const *)
0x1800157c2  mov     rcx, [rsi+28h]
0x1800157c6  mov     [rcx+2Ch], eax
0x1800157c9  jmp     loc_18001545B
0x1800157ce  mov     rdx, rbx; char *
0x1800157d1  mov     rcx, rdi; this
0x1800157d4  call    ?GetFirstWord@CParseXML@@QEAAPEADPEBD@Z; CParseXML::GetFirstWord(char const *)
0x1800157d9  mov     rcx, rax; lpString1
0x1800157dc  lea     rdx, aLastpromptedve_0; "LastPromptedVersion"
0x1800157e3  call    cs:__imp_lstrcmpiA
0x1800157e9  test    eax, eax
0x1800157eb  jnz     short loc_180015817
0x1800157ed  cmp     qword ptr [rsi+28h], 0
0x1800157f2  jz      loc_180015879
0x1800157f8  mov     rdx, rbx; char *
0x1800157fb  mov     rcx, rdi; this
0x1800157fe  call    ?GetValue@CParseXML@@QEAAPEADPEBD@Z; CParseXML::GetValue(char const *)
0x180015803  mov     rcx, rax; char *
0x180015806  call    ?Atoi@@YAHPEBD@Z; Atoi(char const *)
0x18001580b  mov     rcx, [rsi+28h]
0x18001580f  mov     [rcx+30h], eax
0x180015812  jmp     loc_18001545B
0x180015817  mov     rdx, rbx; char *
0x18001581a  mov     rcx, rdi; this
0x18001581d  call    ?GetFirstWord@CParseXML@@QEAAPEADPEBD@Z; CParseXML::GetFirstWord(char const *)
0x180015822  mov     rcx, rax; lpString1
0x180015825  lea     rdx, aColnum_0; "ColNum"
0x18001582c  call    cs:__imp_lstrcmpiA
0x180015832  test    eax, eax
0x180015834  jnz     short loc_180015868
0x180015836  cmp     qword ptr [rsi+28h], 0
0x18001583b  jz      short loc_180015879
0x18001583d  mov     rdx, rbx; char *
0x180015840  mov     rcx, rdi; this
0x180015843  call    ?GetValue@CParseXML@@QEAAPEADPEBD@Z; CParseXML::GetValue(char const *)
0x180015848  mov     rcx, rax; char *
0x18001584b  call    ?Atoi@@YAHPEBD@Z; Atoi(char const *)
0x180015850  mov     rcx, [rsi+28h]
0x180015854  mov     [rcx+28h], eax
0x180015857  jmp     loc_18001545B
0x18001585c  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180015861  mov     eax, 7
0x180015866  jmp     short loc_180015885
0x180015868  test    rbp, rbp
0x18001586b  jz      short loc_180015875
0x18001586d  mov     rcx, rbp; void *
0x180015870  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180015875  xor     eax, eax
0x180015877  jmp     short loc_180015885
0x180015879  mov     eax, 4
0x18001587e  jmp     short loc_180015885
0x180015880  mov     eax, 0Bh
0x180015885  mov     rbx, [rsp+48h+arg_0]
0x18001588a  add     rsp, 20h
0x18001588e  pop     r15
0x180015890  pop     r14
0x180015892  pop     rdi
0x180015893  pop     rsi
0x180015894  pop     rbp
0x180015895  retn
```
