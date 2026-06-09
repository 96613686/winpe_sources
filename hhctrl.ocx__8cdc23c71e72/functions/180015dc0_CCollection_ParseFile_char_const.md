# CCollection::ParseFile(char const *)

- ea: `0x180015dc0`
- end: `0x18001622d`
- name: `?ParseFile@CCollection@@AEAAKPEBD@Z`
- size: `1133`
- prototype: `unsigned int __fastcall(CCollection *__hidden this, const char *)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180015a2c`

## callees

- `0x180001710`
- `0x180014594`
- `0x180014dfc`
- `0x180015010`
- `0x1800150dc`
- `0x1800152bc`
- `0x180015418`
- `0x180015dc0`
- `0x180047854`
- `0x1800478d0`
- `0x1800478fc`
- `0x1800479dc`
- `0x180047a6c`
- `0x180047b7c`
- `0x180047d2c`
- `0x180065438`
- `0x180075c66`
- `0x180075c90`

## import_xrefs

- `KERNEL32!lstrcmpiA` at `0x180015edf`
- `KERNEL32!lstrcmpiA` at `0x180015f20`
- `KERNEL32!lstrcmpiA` at `0x180015f41`
- `KERNEL32!lstrcmpiA` at `0x180015f9c`
- `KERNEL32!lstrcmpiA` at `0x180015fea`
- `KERNEL32!lstrcmpiA` at `0x18001603e`
- `KERNEL32!lstrcmpiA` at `0x18001606c`
- `KERNEL32!lstrcmpiA` at `0x1800160bc`
- `KERNEL32!lstrcmpiA` at `0x1800160dd`
- `KERNEL32!lstrcmpiA` at `0x180016102`
- `KERNEL32!lstrcmpiA` at `0x180015edf`
- `KERNEL32!lstrcmpiA` at `0x180015f20`
- `KERNEL32!lstrcmpiA` at `0x180015f41`
- `KERNEL32!lstrcmpiA` at `0x180015f9c`
- `KERNEL32!lstrcmpiA` at `0x180015fea`
- `KERNEL32!lstrcmpiA` at `0x18001603e`
- `KERNEL32!lstrcmpiA` at `0x18001606c`
- `KERNEL32!lstrcmpiA` at `0x1800160bc`
- `KERNEL32!lstrcmpiA` at `0x1800160dd`
- `KERNEL32!lstrcmpiA` at `0x180016102`

## string_xrefs

- `0x18001614b`: `DocCompilations`
- `0x18001616f`: `DocCompilation`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CCollection::ParseFile(CCollection *this, const char *a2)
{
  unsigned int Tail; // edi
  char *Token; // rbx
  char *v5; // rdi
  char *v6; // rax
  int v7; // r8d
  int v8; // edx
  const CHAR *FirstWord; // rax
  int v10; // eax
  const char *v11; // rdx
  const char *v12; // rax
  const CHAR *v13; // rax
  int v14; // eax
  const CHAR *v15; // rax
  const char *v16; // rax
  unsigned int v17; // eax
  const CHAR *v18; // rax
  const char *v19; // rax
  const CHAR *v20; // rax
  const char *Value; // rax
  unsigned int v22; // eax
  const CHAR *v23; // rax
  int v24; // eax
  const CHAR *v25; // rax
  const char *v26; // rax
  const CHAR *v27; // rax
  int v28; // eax
  const CHAR *v29; // rax
  int v30; // eax
  const CHAR *v31; // rax
  const char *v32; // rax
  const char *v33; // rax
  int v34; // eax
  const char *v35; // rax
  int v36; // eax
  const char *v37; // rax
  char *v39[2]; // [rsp+20h] [rbp-E0h] BYREF
  _QWORD v40[258]; // [rsp+30h] [rbp-D0h] BYREF
  char v41; // [rsp+840h] [rbp+740h]
  __int64 v42; // [rsp+C40h] [rbp+B40h]
  int v43; // [rsp+C48h] [rbp+B48h]

  v40[1] = 0;
  v40[0] = 0;
  v41 = 0;
  v42 = 0;
  v43 = 0;
  v39[0] = 0;
  if ( a2 )
  {
    Tail = CParseXML::Start((CParseXML *)v40, a2);
    if ( !Tail )
    {
LABEL_4:
      while ( 2 )
      {
        Token = CParseXML::GetToken((CParseXML *)v40);
        while ( 1 )
        {
          if ( !Token )
          {
            Tail = 0;
            while ( !CFIFOString::GetTail((CCollection *)((char *)this + 112), v39) )
            {
              operator delete[](v39[0]);
              Tail = 8;
            }
            goto LABEL_48;
          }
          if ( *Token == 47 )
          {
            Tail = CFIFOString::GetTail((CCollection *)((char *)this + 112), v39);
            if ( Tail )
              goto LABEL_48;
            v5 = v39[0];
            v6 = v39[0];
            do
            {
              v7 = (unsigned __int8)v6[Token + 1 - v39[0]];
              v8 = (unsigned __int8)*v6 - v7;
              if ( v8 )
                break;
              ++v6;
            }
            while ( v7 );
            if ( v8 )
            {
              CParseXML::End((CParseXML *)v40);
              operator delete[](v5);
              Tail = 7;
              goto LABEL_49;
            }
            operator delete[](v39[0]);
            if ( !strcmp_0(Token, "/Folder") )
              --*((_DWORD *)this + 230);
            goto LABEL_4;
          }
          FirstWord = CParseXML::GetFirstWord((CParseXML *)v40, Token);
          v10 = lstrcmpiA(FirstWord, "XML");
          v11 = Token;
          if ( !v10 )
            break;
          v13 = CParseXML::GetFirstWord((CParseXML *)v40, Token);
          v14 = lstrcmpiA(v13, "Collections");
          v11 = Token;
          if ( !v14 )
            break;
          v15 = CParseXML::GetFirstWord((CParseXML *)v40, Token);
          if ( lstrcmpiA(v15, "Collection") )
          {
            v18 = CParseXML::GetFirstWord((CParseXML *)v40, Token);
            if ( lstrcmpiA(v18, "HTMLHelpCollection") )
            {
              v20 = CParseXML::GetFirstWord((CParseXML *)v40, Token);
              if ( !lstrcmpiA(v20, "NextCollectionId") )
              {
                Value = CParseXML::GetValue((CParseXML *)v40, Token);
                v22 = Atoi(Value);
                if ( *((_DWORD *)this + 232) < 0xF4240u || v22 >= 0xF4240 )
                  *((_DWORD *)this + 232) = v22;
                goto LABEL_4;
              }
              v23 = CParseXML::GetFirstWord((CParseXML *)v40, Token);
              v24 = lstrcmpiA(v23, "Folders");
              v11 = Token;
              if ( !v24 )
                break;
              v25 = CParseXML::GetFirstWord((CParseXML *)v40, Token);
              if ( lstrcmpiA(v25, "Folder") )
              {
                v27 = CParseXML::GetFirstWord((CParseXML *)v40, Token);
                v28 = lstrcmpiA(v27, "HTMLHelpDocInfo");
                v11 = Token;
                if ( !v28 )
                  break;
                v29 = CParseXML::GetFirstWord((CParseXML *)v40, Token);
                v30 = lstrcmpiA(v29, "Locations");
                v11 = Token;
                if ( !v30 )
                  break;
                v31 = CParseXML::GetFirstWord((CParseXML *)v40, Token);
                if ( lstrcmpiA(v31, "Location") )
                {
                  v33 = CParseXML::GetFirstWord((CParseXML *)v40, Token);
                  v34 = strcmp_0(v33, "DocCompilations");
                  v11 = Token;
                  if ( !v34 )
                    break;
                  v35 = CParseXML::GetFirstWord((CParseXML *)v40, Token);
                  v36 = strcmp_0(v35, "DocCompilation");
                  v11 = Token;
                  if ( v36 )
                    break;
                  v37 = CParseXML::GetFirstWord((CParseXML *)v40, Token);
                  Tail = CFIFOString::AddTail((CCollection *)((char *)this + 112), v37);
                  if ( Tail )
                    goto LABEL_48;
                  v17 = CCollection::HandleTitle(this, (struct CParseXML *)v40, Token);
                }
                else
                {
                  v32 = CParseXML::GetFirstWord((CParseXML *)v40, Token);
                  Tail = CFIFOString::AddTail((CCollection *)((char *)this + 112), v32);
                  if ( Tail )
                    goto LABEL_48;
                  v17 = CCollection::HandleLocation(this, (struct CParseXML *)v40, Token);
                }
              }
              else
              {
                v26 = CParseXML::GetFirstWord((CParseXML *)v40, Token);
                Tail = CFIFOString::AddTail((CCollection *)((char *)this + 112), v26);
                if ( Tail )
                  goto LABEL_48;
                v17 = CCollection::HandleFolder(this, (struct CParseXML *)v40, Token);
              }
            }
            else
            {
              v19 = CParseXML::GetFirstWord((CParseXML *)v40, Token);
              Tail = CFIFOString::AddTail((CCollection *)((char *)this + 112), v19);
              if ( Tail )
                goto LABEL_48;
              v17 = CCollection::HandleCollection(this, (struct CParseXML *)v40, Token);
            }
          }
          else
          {
            v16 = CParseXML::GetFirstWord((CParseXML *)v40, Token);
            Tail = CFIFOString::AddTail((CCollection *)((char *)this + 112), v16);
            if ( Tail )
              goto LABEL_48;
            v17 = CCollection::HandleCollectionEntry(this, (struct CParseXML *)v40, Token);
          }
          Tail = v17;
          if ( v17 )
            goto LABEL_48;
        }
        v12 = CParseXML::GetFirstWord((CParseXML *)v40, v11);
        Tail = CFIFOString::AddTail((CCollection *)((char *)this + 112), v12);
        if ( !Tail )
          continue;
        break;
      }
LABEL_48:
      CParseXML::End((CParseXML *)v40);
    }
  }
  else
  {
    Tail = 11;
  }
LABEL_49:
  CParseXML::~CParseXML((CParseXML *)v40);
  return Tail;
}

```

## disassembly

```asm
0x180015dc0  mov     [rsp-8+arg_10], rbx
0x180015dc5  push    rbp
0x180015dc6  push    rsi
0x180015dc7  push    rdi
0x180015dc8  lea     rbp, [rsp-0B60h]
0x180015dd0  sub     rsp, 0C60h
0x180015dd7  mov     rax, cs:__security_cookie
0x180015dde  xor     rax, rsp
0x180015de1  mov     [rbp+0B70h+var_20], rax
0x180015de8  mov     rsi, rcx
0x180015deb  mov     [rsp+0C70h+var_C38], 0
0x180015df4  mov     [rsp+0C70h+var_C40], 0
0x180015dfd  mov     [rbp+0B70h+var_430], 0
0x180015e04  mov     [rbp+0B70h+var_30], 0
0x180015e0f  mov     [rbp+0B70h+var_28], 0
0x180015e19  mov     [rsp+0C70h+var_C50], 0
0x180015e22  test    rdx, rdx
0x180015e25  jnz     short loc_180015E2F
0x180015e27  lea     edi, [rdx+0Bh]
0x180015e2a  jmp     loc_1800161FF
0x180015e2f  lea     rcx, [rsp+0C70h+var_C40]; this
0x180015e34  call    ?Start@CParseXML@@QEAAKPEBD@Z; CParseXML::Start(char const *)
0x180015e39  mov     edi, eax
0x180015e3b  test    eax, eax
0x180015e3d  jnz     loc_1800161FF
0x180015e43  lea     rcx, [rsp+0C70h+var_C40]; this
0x180015e48  call    ?GetToken@CParseXML@@QEAAPEADXZ; CParseXML::GetToken(void)
0x180015e4d  mov     rbx, rax
0x180015e50  test    rbx, rbx
0x180015e53  jz      loc_1800161CF
0x180015e59  cmp     byte ptr [rbx], 2Fh ; '/'
0x180015e5c  jnz     short loc_180015EC8
0x180015e5e  lea     rcx, [rsi+70h]; this
0x180015e62  lea     rdx, [rsp+0C70h+var_C50]; char **
0x180015e67  call    ?GetTail@CFIFOString@@QEAAKPEAPEAD@Z; CFIFOString::GetTail(char * *)
0x180015e6c  mov     edi, eax
0x180015e6e  test    eax, eax
0x180015e70  jnz     loc_1800161F4
0x180015e76  lea     rcx, [rbx+1]
0x180015e7a  mov     rdi, [rsp+0C70h+var_C50]
0x180015e7f  mov     rax, rdi
0x180015e82  sub     rcx, rdi
0x180015e85  movzx   edx, byte ptr [rax]
0x180015e88  movzx   r8d, byte ptr [rax+rcx]
0x180015e8d  sub     edx, r8d
0x180015e90  jnz     short loc_180015E9A
0x180015e92  inc     rax
0x180015e95  test    r8d, r8d
0x180015e98  jnz     short loc_180015E85
0x180015e9a  test    edx, edx
0x180015e9c  jnz     loc_1800161B6
0x180015ea2  mov     rcx, rdi; void *
0x180015ea5  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180015eaa  lea     rdx, Str2; "/Folder"
0x180015eb1  mov     rcx, rbx; Str1
0x180015eb4  call    strcmp_0
0x180015eb9  test    eax, eax
0x180015ebb  jnz     short loc_180015E43
0x180015ebd  dec     dword ptr [rsi+398h]
0x180015ec3  jmp     loc_180015E43
0x180015ec8  mov     rdx, rbx; char *
0x180015ecb  lea     rcx, [rsp+0C70h+var_C40]; this
0x180015ed0  call    ?GetFirstWord@CParseXML@@QEAAPEADPEBD@Z; CParseXML::GetFirstWord(char const *)
0x180015ed5  mov     rcx, rax; lpString1
0x180015ed8  lea     rdx, aXml_1; "XML"
0x180015edf  call    cs:__imp_lstrcmpiA
0x180015ee5  mov     rdx, rbx; char *
0x180015ee8  lea     rcx, [rsp+0C70h+var_C40]; this
0x180015eed  test    eax, eax
0x180015eef  jnz     short loc_180015F11
0x180015ef1  call    ?GetFirstWord@CParseXML@@QEAAPEADPEBD@Z; CParseXML::GetFirstWord(char const *)
0x180015ef6  lea     rcx, [rsi+70h]; this
0x180015efa  mov     rdx, rax; char *
0x180015efd  call    ?AddTail@CFIFOString@@QEAAKPEBD@Z; CFIFOString::AddTail(char const *)
0x180015f02  mov     edi, eax
0x180015f04  test    eax, eax
0x180015f06  jnz     loc_1800161F4
0x180015f0c  jmp     loc_180015E43
0x180015f11  call    ?GetFirstWord@CParseXML@@QEAAPEADPEBD@Z; CParseXML::GetFirstWord(char const *)
0x180015f16  mov     rcx, rax; lpString1
0x180015f19  lea     rdx, aCollections_1; "Collections"
0x180015f20  call    cs:__imp_lstrcmpiA
0x180015f26  mov     rdx, rbx; char *
0x180015f29  lea     rcx, [rsp+0C70h+var_C40]; this
0x180015f2e  test    eax, eax
0x180015f30  jz      short loc_180015EF1
0x180015f32  call    ?GetFirstWord@CParseXML@@QEAAPEADPEBD@Z; CParseXML::GetFirstWord(char const *)
0x180015f37  mov     rcx, rax; lpString1
0x180015f3a  lea     rdx, aCollection; "Collection"
0x180015f41  call    cs:__imp_lstrcmpiA
0x180015f47  mov     rdx, rbx; char *
0x180015f4a  lea     rcx, [rsp+0C70h+var_C40]; this
0x180015f4f  test    eax, eax
0x180015f51  jnz     short loc_180015F8D
0x180015f53  call    ?GetFirstWord@CParseXML@@QEAAPEADPEBD@Z; CParseXML::GetFirstWord(char const *)
0x180015f58  mov     rdx, rax; char *
0x180015f5b  lea     rcx, [rsi+70h]; this
0x180015f5f  call    ?AddTail@CFIFOString@@QEAAKPEBD@Z; CFIFOString::AddTail(char const *)
0x180015f64  mov     edi, eax
0x180015f66  test    eax, eax
0x180015f68  jnz     loc_1800161F4
0x180015f6e  mov     r8, rbx; char *
0x180015f71  lea     rdx, [rsp+0C70h+var_C40]; struct CParseXML *
0x180015f76  mov     rcx, rsi; this
0x180015f79  call    ?HandleCollectionEntry@CCollection@@AEAAKPEAVCParseXML@@PEAD@Z; CCollection::HandleCollectionEntry(CParseXML *,char *)
0x180015f7e  mov     edi, eax
0x180015f80  test    eax, eax
0x180015f82  jz      loc_180015E50
0x180015f88  jmp     loc_1800161F4
0x180015f8d  call    ?GetFirstWord@CParseXML@@QEAAPEADPEBD@Z; CParseXML::GetFirstWord(char const *)
0x180015f92  mov     rcx, rax; lpString1
0x180015f95  lea     rdx, aHtmlhelpcollec; "HTMLHelpCollection"
0x180015f9c  call    cs:__imp_lstrcmpiA
0x180015fa2  mov     rdx, rbx; char *
0x180015fa5  lea     rcx, [rsp+0C70h+var_C40]; this
0x180015faa  test    eax, eax
0x180015fac  jnz     short loc_180015FDB
0x180015fae  call    ?GetFirstWord@CParseXML@@QEAAPEADPEBD@Z; CParseXML::GetFirstWord(char const *)
0x180015fb3  mov     rdx, rax; char *
0x180015fb6  lea     rcx, [rsi+70h]; this
0x180015fba  call    ?AddTail@CFIFOString@@QEAAKPEBD@Z; CFIFOString::AddTail(char const *)
0x180015fbf  mov     edi, eax
0x180015fc1  test    eax, eax
0x180015fc3  jnz     loc_1800161F4
0x180015fc9  mov     r8, rbx; char *
0x180015fcc  lea     rdx, [rsp+0C70h+var_C40]; struct CParseXML *
0x180015fd1  mov     rcx, rsi; this
0x180015fd4  call    ?HandleCollection@CCollection@@AEAAKPEAVCParseXML@@PEAD@Z; CCollection::HandleCollection(CParseXML *,char *)
0x180015fd9  jmp     short loc_180015F7E
0x180015fdb  call    ?GetFirstWord@CParseXML@@QEAAPEADPEBD@Z; CParseXML::GetFirstWord(char const *)
0x180015fe0  mov     rcx, rax; lpString1
0x180015fe3  lea     rdx, aNextcollection_0; "NextCollectionId"
0x180015fea  call    cs:__imp_lstrcmpiA
0x180015ff0  mov     rdx, rbx; char *
0x180015ff3  lea     rcx, [rsp+0C70h+var_C40]; this
0x180015ff8  test    eax, eax
0x180015ffa  jnz     short loc_18001602B
0x180015ffc  call    ?GetValue@CParseXML@@QEAAPEADPEBD@Z; CParseXML::GetValue(char const *)
0x180016001  mov     rcx, rax; char *
0x180016004  call    ?Atoi@@YAHPEBD@Z; Atoi(char const *)
0x180016009  cmp     dword ptr [rsi+3A0h], 0F4240h
0x180016013  jb      short loc_180016020
0x180016015  cmp     eax, 0F4240h
0x18001601a  jb      loc_180015E43
0x180016020  mov     [rsi+3A0h], eax
0x180016026  jmp     loc_180015E43
0x18001602b  lea     rdi, [rsi+70h]
0x18001602f  call    ?GetFirstWord@CParseXML@@QEAAPEADPEBD@Z; CParseXML::GetFirstWord(char const *)
0x180016034  mov     rcx, rax; lpString1
0x180016037  lea     rdx, aFolders; "Folders"
0x18001603e  call    cs:__imp_lstrcmpiA
0x180016044  mov     rdx, rbx; char *
0x180016047  lea     rcx, [rsp+0C70h+var_C40]; this
0x18001604c  test    eax, eax
0x18001604e  jnz     short loc_18001605D
0x180016050  call    ?GetFirstWord@CParseXML@@QEAAPEADPEBD@Z; CParseXML::GetFirstWord(char const *)
0x180016055  mov     rcx, rdi
0x180016058  jmp     loc_180015EFA
0x18001605d  call    ?GetFirstWord@CParseXML@@QEAAPEADPEBD@Z; CParseXML::GetFirstWord(char const *)
0x180016062  mov     rcx, rax; lpString1
0x180016065  lea     rdx, aFolder; "Folder"
0x18001606c  call    cs:__imp_lstrcmpiA
0x180016072  mov     rdx, rbx; char *
0x180016075  lea     rcx, [rsp+0C70h+var_C40]; this
0x18001607a  test    eax, eax
0x18001607c  jnz     short loc_1800160AD
0x18001607e  call    ?GetFirstWord@CParseXML@@QEAAPEADPEBD@Z; CParseXML::GetFirstWord(char const *)
0x180016083  mov     rdx, rax; char *
0x180016086  mov     rcx, rdi; this
0x180016089  call    ?AddTail@CFIFOString@@QEAAKPEBD@Z; CFIFOString::AddTail(char const *)
0x18001608e  mov     edi, eax
0x180016090  test    eax, eax
0x180016092  jnz     loc_1800161F4
0x180016098  mov     r8, rbx; char *
0x18001609b  lea     rdx, [rsp+0C70h+var_C40]; struct CParseXML *
0x1800160a0  mov     rcx, rsi; this
0x1800160a3  call    ?HandleFolder@CCollection@@AEAAKPEAVCParseXML@@PEAD@Z; CCollection::HandleFolder(CParseXML *,char *)
0x1800160a8  jmp     loc_180015F7E
0x1800160ad  call    ?GetFirstWord@CParseXML@@QEAAPEADPEBD@Z; CParseXML::GetFirstWord(char const *)
0x1800160b2  mov     rcx, rax; lpString1
0x1800160b5  lea     rdx, aHtmlhelpdocinf_1; "HTMLHelpDocInfo"
0x1800160bc  call    cs:__imp_lstrcmpiA
0x1800160c2  mov     rdx, rbx; char *
0x1800160c5  lea     rcx, [rsp+0C70h+var_C40]; this
0x1800160ca  test    eax, eax
0x1800160cc  jz      short loc_180016050
0x1800160ce  call    ?GetFirstWord@CParseXML@@QEAAPEADPEBD@Z; CParseXML::GetFirstWord(char const *)
0x1800160d3  mov     rcx, rax; lpString1
0x1800160d6  lea     rdx, aLocations; "Locations"
0x1800160dd  call    cs:__imp_lstrcmpiA
0x1800160e3  mov     rdx, rbx; char *
0x1800160e6  lea     rcx, [rsp+0C70h+var_C40]; this
0x1800160eb  test    eax, eax
0x1800160ed  jz      loc_180016050
0x1800160f3  call    ?GetFirstWord@CParseXML@@QEAAPEADPEBD@Z; CParseXML::GetFirstWord(char const *)
0x1800160f8  mov     rcx, rax; lpString1
0x1800160fb  lea     rdx, aLocation_0; "Location"
0x180016102  call    cs:__imp_lstrcmpiA
0x180016108  mov     rdx, rbx; char *
0x18001610b  lea     rcx, [rsp+0C70h+var_C40]; this
0x180016110  test    eax, eax
0x180016112  jnz     short loc_180016143
0x180016114  call    ?GetFirstWord@CParseXML@@QEAAPEADPEBD@Z; CParseXML::GetFirstWord(char const *)
0x180016119  mov     rdx, rax; char *
0x18001611c  mov     rcx, rdi; this
0x18001611f  call    ?AddTail@CFIFOString@@QEAAKPEBD@Z; CFIFOString::AddTail(char const *)
0x180016124  mov     edi, eax
0x180016126  test    eax, eax
0x180016128  jnz     loc_1800161F4
0x18001612e  mov     r8, rbx; char *
0x180016131  lea     rdx, [rsp+0C70h+var_C40]; struct CParseXML *
0x180016136  mov     rcx, rsi; this
0x180016139  call    ?HandleLocation@CCollection@@AEAAKPEAVCParseXML@@PEAD@Z; CCollection::HandleLocation(CParseXML *,char *)
0x18001613e  jmp     loc_180015F7E
0x180016143  call    ?GetFirstWord@CParseXML@@QEAAPEADPEBD@Z; CParseXML::GetFirstWord(char const *)
0x180016148  mov     rcx, rax; Str1
0x18001614b  lea     rdx, aDoccompilation_3; "DocCompilations"
0x180016152  call    strcmp_0
0x180016157  mov     rdx, rbx; char *
0x18001615a  lea     rcx, [rsp+0C70h+var_C40]; this
0x18001615f  test    eax, eax
0x180016161  jz      loc_180016050
0x180016167  call    ?GetFirstWord@CParseXML@@QEAAPEADPEBD@Z; CParseXML::GetFirstWord(char const *)
0x18001616c  mov     rcx, rax; Str1
0x18001616f  lea     rdx, aDoccompilation; "DocCompilation"
0x180016176  call    strcmp_0
0x18001617b  mov     rdx, rbx; char *
0x18001617e  lea     rcx, [rsp+0C70h+var_C40]; this
0x180016183  test    eax, eax
0x180016185  jnz     loc_180016050
0x18001618b  call    ?GetFirstWord@CParseXML@@QEAAPEADPEBD@Z; CParseXML::GetFirstWord(char const *)
0x180016190  mov     rdx, rax; char *
0x180016193  mov     rcx, rdi; this
0x180016196  call    ?AddTail@CFIFOString@@QEAAKPEBD@Z; CFIFOString::AddTail(char const *)
0x18001619b  mov     edi, eax
0x18001619d  test    eax, eax
0x18001619f  jnz     short loc_1800161F4
0x1800161a1  mov     r8, rbx; char *
0x1800161a4  lea     rdx, [rsp+0C70h+var_C40]; struct CParseXML *
0x1800161a9  mov     rcx, rsi; this
0x1800161ac  call    ?HandleTitle@CCollection@@AEAAKPEAVCParseXML@@PEAD@Z; CCollection::HandleTitle(CParseXML *,char *)
0x1800161b1  jmp     loc_180015F7E
0x1800161b6  lea     rcx, [rsp+0C70h+var_C40]; this
0x1800161bb  call    ?End@CParseXML@@QEAAXXZ; CParseXML::End(void)
0x1800161c0  mov     rcx, rdi; void *
0x1800161c3  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x1800161c8  mov     edi, 7
0x1800161cd  jmp     short loc_1800161FF
0x1800161cf  xor     edi, edi
0x1800161d1  jmp     short loc_1800161E2
0x1800161d3  mov     rcx, [rsp+0C70h+var_C50]; void *
0x1800161d8  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x1800161dd  mov     edi, 8
0x1800161e2  lea     rdx, [rsp+0C70h+var_C50]; char **
0x1800161e7  lea     rcx, [rsi+70h]; this
0x1800161eb  call    ?GetTail@CFIFOString@@QEAAKPEAPEAD@Z; CFIFOString::GetTail(char * *)
0x1800161f0  test    eax, eax
0x1800161f2  jz      short loc_1800161D3
0x1800161f4  lea     rcx, [rsp+0C70h+var_C40]; this
0x1800161f9  call    ?End@CParseXML@@QEAAXXZ; CParseXML::End(void)
0x1800161fe  nop
0x1800161ff  lea     rcx, [rsp+0C70h+var_C40]; this
0x180016204  call    ??1CParseXML@@QEAA@XZ; CParseXML::~CParseXML(void)
0x180016209  mov     eax, edi
0x18001620b  mov     rcx, [rbp+0B70h+var_20]
0x180016212  xor     rcx, rsp; StackCookie
0x180016215  call    __security_check_cookie
0x18001621a  mov     rbx, [rsp+0C70h+arg_10]
0x180016222  add     rsp, 0C60h
0x180016229  pop     rdi
0x18001622a  pop     rsi
0x18001622b  pop     rbp
0x18001622c  retn
```
