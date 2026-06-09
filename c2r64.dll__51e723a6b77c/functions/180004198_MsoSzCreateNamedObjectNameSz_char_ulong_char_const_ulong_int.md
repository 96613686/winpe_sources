# MsoSzCreateNamedObjectNameSz(char *,ulong,char const *,ulong,int)

- ea: `0x180004198`
- end: `0x180004474`
- name: `?MsoSzCreateNamedObjectNameSz@@YAPEADPEADKPEBDKH@Z`
- size: `732`
- prototype: `char *__usercall@<rax>(char *Destination@<rcx>, unsigned int@<edx>, const char *@<r8>, unsigned int@<r9d>, int)`
- caller_count: `5`
- callee_count: `14`
- tags: `reparse_path, authz_impersonation`

## callers

- `0x180004080`
- `0x180037cf4`
- `0x180121d78`
- `0x180121ee8`
- `0x180122030`

## callees

- `0x180004198`
- `0x180004568`
- `0x1800045a8`
- `0x1800264b4`
- `0x180033838`
- `0x180039748`
- `0x18003e690`
- `0x180052cd0`
- `0x18009f84c`
- `0x180122178`
- `0x180122580`
- `0x180123508`
- `0x180123538`
- `0x180146440`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180004468`
- `KERNEL32!LocalFree` at `0x180004468`
- `KERNEL32!GlobalFree` at `0x1800043d8`
- `KERNEL32!GlobalFree` at `0x1800043d8`
- `ADVAPI32!ConvertSidToStringSidA` at `0x1800043b5`
- `ADVAPI32!ConvertSidToStringSidA` at `0x1800043b5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char *__fastcall MsoSzCreateNamedObjectNameSz(char *Destination, __int64 a2, const char *a3, __int16 a4, int a5)
{
  __int16 v5; // di
  char *v8; // r14
  void *v9; // rsi
  const char *v10; // rcx
  Mso::Process *v11; // rcx
  const wchar_t *SuiteName; // rax
  int v14; // eax
  char *v15; // rsi
  size_t v16; // r14
  LPVOID v17; // rcx
  BOOL UserSid; // eax
  unsigned __int16 *Version; // rax
  LPSTR StringSid; // [rsp+30h] [rbp-30h] BYREF
  _OWORD Src[2]; // [rsp+38h] [rbp-28h] BYREF

  v5 = a4;
  StringSid = 0;
  v8 = 0;
  v9 = 0;
  *(_QWORD *)&Src[0] = 0;
  if ( (a4 & 0x100) == 0 )
  {
    if ( !Destination || !a3 )
    {
      MsoShipAssertTagProc(1422243);
LABEL_17:
      if ( StringSid )
        LocalFree(StringSid);
      return v8;
    }
    if ( (a4 & 0x800) != 0 )
    {
      MsoSzCopy(a3, Destination, (int)a3);
LABEL_16:
      v8 = Destination;
      goto LABEL_17;
    }
    if ( (a4 & 0x10) != 0 )
    {
      MsoPsaLogonIdDacl(a5);
      v17 = vpLogonIdSID;
      if ( vpLogonIdSID )
        goto LABEL_42;
      MsoShipAssertTagProc(1422273);
      v17 = vpLogonIdSID;
    }
    else if ( (a4 & 0x20) != 0 )
    {
      MsoPsaUserDacl(a5);
      v17 = vpUserSID;
      if ( vpUserSID )
        goto LABEL_42;
      MsoShipAssertTagProc(1422274);
      v17 = vpUserSID;
    }
    else
    {
      if ( (a4 & 0x40) == 0 )
      {
LABEL_8:
        v10 = "Global\\";
        if ( (v5 & 1) == 0 )
          v10 = "Local\\";
        MsoSzCopy(v10, Destination, (int)a3);
        MsoSzAppend(a3, Destination);
        if ( (v5 & 0x1000) != 0 )
        {
          SuiteName = Mso::Process::GetSuiteName(v11);
          memset(Src, 0, sizeof(Src));
          sprintf_s<32>(Src, "%S", SuiteName);
          v14 = 1024;
          v15 = Destination;
          do
          {
            if ( !*v15 )
              break;
            ++v15;
            --v14;
          }
          while ( v14 > 0 );
          if ( v14 <= 0 )
          {
            MsoShipAssertTagProc(1090305);
          }
          else
          {
            if ( !v15 )
              CrashWithRecovery(0x27D300Eu, 0);
            v16 = -1;
            do
              ++v16;
            while ( *((_BYTE *)Src + v16) );
            if ( (unsigned __int64)(unsigned int)v14 - 1 < v16 )
              v16 = (unsigned int)v14 - 1LL;
            memmove(v15, Src, v16);
            v15[v16] = 0;
          }
        }
        if ( (v5 & 0x80u) != 0 )
        {
          Version = (unsigned __int16 *)Mso::Process::GetVersion(v11);
          sprintf_s<16>(Src, "%d%d%4d", Version[1], *Version, Version[3]);
          MsoSzAppend(Src, Destination);
        }
        if ( (v5 & 0x200) != 0 )
          MsoSzAppend(&qword_18021A2B0, Destination);
        if ( (v5 & 0x70) != 0 && StringSid )
        {
          MsoSzAppend("_", Destination);
          MsoSzAppend(StringSid, Destination);
        }
        goto LABEL_16;
      }
      UserSid = FAllocateAndRetrieveUserSid(2, (void **)Src);
      v9 = *(void **)&Src[0];
      if ( !UserSid )
        goto LABEL_44;
      v17 = *(LPVOID *)&Src[0];
    }
    if ( v17 )
    {
LABEL_42:
      if ( !ConvertSidToStringSidA(v17, &StringSid) )
      {
        MsoShipAssertTagProc(1422276);
        v5 &= 0xFF8Fu;
      }
    }
LABEL_44:
    if ( v9 )
      GlobalFree(v9);
    goto LABEL_8;
  }
  if ( Destination )
    *Destination = 0;
  return v8;
}

```

## disassembly

```asm
0x180004198  mov     [rsp-28h+arg_8], rbx
0x18000419d  push    rbp
0x18000419e  push    rsi
0x18000419f  push    rdi
0x1800041a0  push    r14
0x1800041a2  push    r15
0x1800041a4  mov     rbp, rsp
0x1800041a7  sub     rsp, 60h
0x1800041ab  mov     rax, cs:__security_cookie
0x1800041b2  xor     rax, rsp
0x1800041b5  mov     [rbp+var_8], rax
0x1800041b9  mov     edi, r9d
0x1800041bc  mov     r15, r8
0x1800041bf  mov     rbx, rcx
0x1800041c2  mov     [rbp+StringSid], 0
0x1800041ca  xor     r14d, r14d
0x1800041cd  xor     esi, esi
0x1800041cf  mov     qword ptr [rbp+Src], rsi
0x1800041d3  bt      r9d, 8
0x1800041d8  jb      loc_180004298
0x1800041de  test    rcx, rcx
0x1800041e1  jz      loc_1800042A2
0x1800041e7  test    r8, r8
0x1800041ea  jz      loc_1800042A2
0x1800041f0  bt      r9d, 0Bh
0x1800041f5  jb      loc_1800042AE
0x1800041fb  test    dil, 10h
0x1800041ff  jnz     loc_180004345
0x180004205  test    dil, 20h
0x180004209  jnz     loc_18000436C
0x18000420f  test    dil, 40h
0x180004213  jnz     loc_180004393
0x180004219  test    dil, 1
0x18000421d  lea     rax, aLocal; "Local\\"
0x180004224  lea     rcx, aGlobal_1; "Global\\"
0x18000422b  cmovz   rcx, rax; Source
0x18000422f  mov     rdx, rbx; Destination
0x180004232  call    ?MsoSzCopy@@YAPEADPEBDPEADH@Z; MsoSzCopy(char const *,char *,int)
0x180004237  mov     rdx, rbx
0x18000423a  mov     rcx, r15
0x18000423d  call    MsoSzAppend
0x180004242  bt      edi, 0Ch
0x180004246  jb      short loc_1800042BB
0x180004248  test    dil, dil
0x18000424b  js      loc_1800043F2
0x180004251  bt      edi, 9
0x180004255  jb      loc_180004429
0x18000425b  test    dil, 70h
0x18000425f  jnz     loc_18000443D
0x180004265  mov     r14, rbx
0x180004268  mov     rcx, [rbp+StringSid]; hMem
0x18000426c  test    rcx, rcx
0x18000426f  jnz     loc_180004468
0x180004275  mov     rax, r14
0x180004278  mov     rcx, [rbp+var_8]
0x18000427c  xor     rcx, rsp; StackCookie
0x18000427f  call    __security_check_cookie
0x180004284  mov     rbx, [rsp+60h+arg_8]
0x18000428c  add     rsp, 60h
0x180004290  pop     r15
0x180004292  pop     r14
0x180004294  pop     rdi
0x180004295  pop     rsi
0x180004296  pop     rbp
0x180004297  retn
0x180004298  test    rbx, rbx
0x18000429b  jz      short loc_180004275
0x18000429d  mov     [rcx], sil
0x1800042a0  jmp     short loc_180004275
0x1800042a2  mov     ecx, 15B3A3h
0x1800042a7  call    MsoShipAssertTagProc
0x1800042ac  jmp     short loc_180004268
0x1800042ae  mov     rdx, rbx; Destination
0x1800042b1  mov     rcx, r15; Source
0x1800042b4  call    ?MsoSzCopy@@YAPEADPEBDPEADH@Z; MsoSzCopy(char const *,char *,int)
0x1800042b9  jmp     short loc_180004265
0x1800042bb  call    ?GetSuiteName@Process@Mso@@YAPEB_WXZ; Mso::Process::GetSuiteName(void)
0x1800042c0  xorps   xmm0, xmm0
0x1800042c3  movups  [rbp+Src], xmm0
0x1800042c7  movups  [rbp+var_18], xmm0
0x1800042cb  mov     r8, rax
0x1800042ce  lea     rdx, aS; "%S"
0x1800042d5  lea     rcx, [rbp+Src]
0x1800042d9  call    ??$sprintf_s@$0CA@@@YAHAEAY0CA@DPEBDZZ; sprintf_s<32>(char (&)[32],char const *,...)
0x1800042de  mov     eax, 400h
0x1800042e3  mov     rsi, rbx
0x1800042e6  cmp     [rsi], r14b
0x1800042e9  jz      short loc_1800042F4
0x1800042eb  inc     rsi
0x1800042ee  dec     eax
0x1800042f0  test    eax, eax
0x1800042f2  jg      short loc_1800042E6
0x1800042f4  test    eax, eax
0x1800042f6  jle     loc_1800043E3
0x1800042fc  test    rsi, rsi
0x1800042ff  jnz     short loc_18000430E
0x180004301  xor     edx, edx; struct CrashContext *
0x180004303  mov     ecx, 27D300Eh; unsigned int
0x180004308  call    ?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x18000430e  mov     ecx, eax
0x180004310  dec     rcx
0x180004313  lea     rax, [rbp+Src]
0x180004317  or      r14, 0FFFFFFFFFFFFFFFFh
0x18000431b  inc     r14
0x18000431e  cmp     byte ptr [rax+r14], 0
0x180004323  jnz     short loc_18000431B
0x180004325  cmp     rcx, r14
0x180004328  cmovb   r14, rcx
0x18000432c  mov     r8, r14; Size
0x18000432f  lea     rdx, [rbp+Src]; Src
0x180004333  mov     rcx, rsi; void *
0x180004336  call    memmove
0x18000433b  mov     byte ptr [r14+rsi], 0
0x180004340  jmp     loc_180004248
0x180004345  mov     ecx, [rbp+arg_20]; int
0x180004348  call    ?MsoPsaLogonIdDacl@@YAPEAU_SECURITY_ATTRIBUTES@@H@Z; MsoPsaLogonIdDacl(int)
0x18000434d  mov     rcx, cs:?vpLogonIdSID@@3PEAXEA; void * vpLogonIdSID
0x180004354  test    rcx, rcx
0x180004357  jnz     short loc_1800043B1
0x180004359  mov     ecx, 15B3C1h
0x18000435e  call    MsoShipAssertTagProc
0x180004363  mov     rcx, cs:?vpLogonIdSID@@3PEAXEA; void * vpLogonIdSID
0x18000436a  jmp     short loc_1800043AC
0x18000436c  mov     ecx, [rbp+arg_20]; int
0x18000436f  call    ?MsoPsaUserDacl@@YAPEAU_SECURITY_ATTRIBUTES@@H@Z; MsoPsaUserDacl(int)
0x180004374  mov     rcx, cs:?vpUserSID@@3PEAXEA; void * vpUserSID
0x18000437b  test    rcx, rcx
0x18000437e  jnz     short loc_1800043B1
0x180004380  mov     ecx, 15B3C2h
0x180004385  call    MsoShipAssertTagProc
0x18000438a  mov     rcx, cs:?vpUserSID@@3PEAXEA; void * vpUserSID
0x180004391  jmp     short loc_1800043AC
0x180004393  lea     rdx, [rbp+Src]; void **
0x180004397  mov     ecx, 2; unsigned int
0x18000439c  call    ?FAllocateAndRetrieveUserSid@@YAHKPEAPEAX@Z; FAllocateAndRetrieveUserSid(ulong,void * *)
0x1800043a1  mov     rsi, qword ptr [rbp+Src]
0x1800043a5  test    eax, eax
0x1800043a7  jz      short loc_1800043CC
0x1800043a9  mov     rcx, rsi; Sid
0x1800043ac  test    rcx, rcx
0x1800043af  jz      short loc_1800043CC
0x1800043b1  lea     rdx, [rbp+StringSid]; StringSid
0x1800043b5  call    cs:__imp_ConvertSidToStringSidA
0x1800043bb  test    eax, eax
0x1800043bd  jnz     short loc_1800043CC
0x1800043bf  mov     ecx, 15B3C4h
0x1800043c4  call    MsoShipAssertTagProc
0x1800043c9  and     edi, 0FFFFFF8Fh
0x1800043cc  test    rsi, rsi
0x1800043cf  jz      loc_180004219
0x1800043d5  mov     rcx, rsi; hMem
0x1800043d8  call    cs:__imp_GlobalFree
0x1800043de  jmp     loc_180004219
0x1800043e3  mov     ecx, 10A301h
0x1800043e8  call    MsoShipAssertTagProc
0x1800043ed  jmp     loc_180004248
0x1800043f2  call    ?GetVersion@Process@Mso@@YAAEBUVersionNumbers@@XZ; Mso::Process::GetVersion(void)
0x1800043f7  movzx   ecx, word ptr [rax+6]
0x1800043fb  movzx   r9d, word ptr [rax]
0x1800043ff  movzx   r8d, word ptr [rax+2]
0x180004404  mov     [rsp+60h+var_40], ecx
0x180004408  lea     rdx, aDD4d; "%d%d%4d"
0x18000440f  lea     rcx, [rbp+Src]
0x180004413  call    ??$sprintf_s@$0BA@@@YAHAEAY0BA@DPEBDZZ; sprintf_s<16>(char (&)[16],char const *,...)
0x180004418  mov     rdx, rbx
0x18000441b  lea     rcx, [rbp+Src]
0x18000441f  call    MsoSzAppend
0x180004424  jmp     loc_180004251
0x180004429  mov     rdx, rbx
0x18000442c  lea     rcx, qword_18021A2B0
0x180004433  call    MsoSzAppend
0x180004438  jmp     loc_18000425B
0x18000443d  cmp     [rbp+StringSid], 0
0x180004442  jz      loc_180004265
0x180004448  mov     rdx, rbx
0x18000444b  lea     rcx, asc_18019E688; "_"
0x180004452  call    MsoSzAppend
0x180004457  mov     rdx, rbx
0x18000445a  mov     rcx, [rbp+StringSid]
0x18000445e  call    MsoSzAppend
0x180004463  jmp     loc_180004265
0x180004468  call    cs:__imp_LocalFree
0x18000446e  jmp     loc_180004275
```
