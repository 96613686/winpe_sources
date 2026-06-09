# SleepstudyJsonReporter::TransformReport(ushort const *,ushort const *)

- ea: `0x18007b860`
- end: `0x18007baa0`
- name: `?TransformReport@SleepstudyJsonReporter@@SAJPEBG0@Z`
- size: `576`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, registry_config`

## callers

- `0x180077ec0`

## callees

- `0x180042fac`
- `0x18004424c`
- `0x180044608`
- `0x18004adac`
- `0x18004ca90`
- `0x18005ee9c`
- `0x18005f01c`
- `0x18005f140`
- `0x18007a968`
- `0x18007aa54`
- `0x18007ad90`
- `0x18007af18`
- `0x18007b3e4`
- `0x18007b750`
- `0x18007b860`
- `0x18007e388`
- `0x18007e900`
- `0x18007eb18`

## string_xrefs

- `0x18007b98f`: `IDR_SLEEPSTUDY_TEMPLATE_CSS`
- `0x18007b9f1`: `IDR_SLEEPSTUDY_TEMPLATE_HTML`
- `0x18007b9c2`: `IDR_SLEEPSTUDY_TEMPLATE_JS`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall SleepstudyJsonReporter::TransformReport(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  _QWORD *v4; // rax
  unsigned int FileContents; // ebx
  __int64 v6; // rcx
  _QWORD *v7; // rax
  _BYTE *v8; // rcx
  __int128 v10; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v11[16]; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v12[34]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v13[4]; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v14[32]; // [rsp+170h] [rbp+70h] BYREF
  _BYTE v15[32]; // [rsp+190h] [rbp+90h] BYREF
  _BYTE v16[32]; // [rsp+1B0h] [rbp+B0h] BYREF

  std::string::string(v14);
  std::ofstream::ofstream(v12);
  std::string::string(v13);
  v10 = 0;
  std::_Tree<std::_Tmap_traits<std::string,std::string,std::less<std::string>,std::allocator<std::pair<std::string const,std::string>>,0>>::_Alloc_sentinel_and_proxy(&v10);
  std::string::string(v16);
  std::_Tree<std::_Tmap_traits<std::string,std::string,std::less<std::string>,std::allocator<std::pair<std::string const,std::string>>,0>>::clear(&v10);
  std::string::string(v15, "'__LOCAL_SPR_DATA__'");
  v4 = (_QWORD *)std::map<std::string,std::string>::_Try_emplace<std::string,>(&v10, v11, v15);
  FileContents = ReadFileContents((__int64)a1, *v4 + 64LL);
  std::string::_Tidy_deallocate(v15);
  if ( !FileContents )
  {
    FileContents = SleepstudyJsonReporter::LoadResourceWithReplace(v6, &v10, v14);
    if ( !FileContents )
    {
      std::_Tree<std::_Tmap_traits<std::string,std::string,std::less<std::string>,std::allocator<std::pair<std::string const,std::string>>,0>>::clear(&v10);
      v7 = (_QWORD *)std::map<std::string,std::string>::_Try_emplace<std::string const &,>(&v10, v11, &qword_1800C8C80);
      std::string::operator=(*v7 + 64LL, v14);
      std::map<std::string,std::string>::_Try_emplace<std::string const &,>(&v10, v11, &qword_1800C8CA0);
      FileContents = ReadResourceContents(L"IDR_SLEEPSTUDY_TEMPLATE_CSS");
      if ( !FileContents )
      {
        std::map<std::string,std::string>::_Try_emplace<std::string const &,>(&v10, v11, &qword_1800C8CF0);
        FileContents = ReadResourceContents(L"IDR_SLEEPSTUDY_TEMPLATE_JS");
        if ( !FileContents )
        {
          std::map<std::string,std::string>::_Try_emplace<std::string const &,>(&v10, v11, &qword_1800C8CC0);
          FileContents = ReadResourceContents(L"IDR_SLEEPSTUDY_TEMPLATE_HTML");
          if ( !FileContents )
          {
            FileContents = ReadResourceContents(L"IDR_SLEEPSTUDY_LOCAL_HTML");
            if ( !FileContents )
            {
              std::ofstream::open(v12, a2);
              v8 = v13;
              if ( v13[3] > 0xFu )
                v8 = (_BYTE *)v13[0];
              StringReplaceAll(v8, (__int64)&v10, (__int64)v12);
            }
          }
        }
      }
    }
  }
  std::string::_Tidy_deallocate(v16);
  std::_Tree<std::_Tmap_traits<std::string,std::string,std::less<std::string>,std::allocator<std::pair<std::string const,std::string>>,0>>::~_Tree<std::_Tmap_traits<std::string,std::string,std::less<std::string>,std::allocator<std::pair<std::string const,std::string>>,0>>(&v10);
  std::string::_Tidy_deallocate(v13);
  std::ofstream::`vbase destructor'(v12);
  std::string::_Tidy_deallocate(v14);
  return FileContents;
}

```

## disassembly

```asm
0x18007b860  mov     [rsp-8+arg_10], rbx
0x18007b865  mov     [rsp-8+arg_18], rdi
0x18007b86a  push    rbp
0x18007b86b  lea     rbp, [rsp-0E0h]
0x18007b873  sub     rsp, 1E0h
0x18007b87a  mov     rax, cs:__security_cookie
0x18007b881  xor     rax, rsp
0x18007b884  mov     [rbp+0E0h+var_10], rax
0x18007b88b  mov     rdi, rdx
0x18007b88e  mov     rbx, rcx
0x18007b891  lea     rcx, [rbp+0E0h+var_70]
0x18007b895  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::string(void)
0x18007b89a  nop
0x18007b89b  lea     rcx, [rsp+1E0h+var_1A0]
0x18007b8a0  call    ??0?$basic_ofstream@DU?$char_traits@D@std@@@std@@QEAA@XZ; std::ofstream::ofstream(void)
0x18007b8a5  nop
0x18007b8a6  lea     rcx, [rbp+0E0h+var_90]
0x18007b8aa  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::string(void)
0x18007b8af  nop
0x18007b8b0  xorps   xmm1, xmm1
0x18007b8b3  movdqu  [rsp+1E0h+var_1C0], xmm1
0x18007b8b9  lea     rcx, [rsp+1E0h+var_1C0]
0x18007b8be  call    ?_Alloc_sentinel_and_proxy@?$_Tree@V?$_Tmap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tmap_traits<std::string,std::string,std::less<std::string>,std::allocator<std::pair<std::string const,std::string>>,0>>::_Alloc_sentinel_and_proxy(void)
0x18007b8c3  nop
0x18007b8c4  lea     rcx, [rbp+0E0h+var_30]
0x18007b8cb  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::string(void)
0x18007b8d0  nop
0x18007b8d1  lea     rcx, [rsp+1E0h+var_1C0]
0x18007b8d6  call    ?clear@?$_Tree@V?$_Tmap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAAXXZ; std::_Tree<std::_Tmap_traits<std::string,std::string,std::less<std::string>,std::allocator<std::pair<std::string const,std::string>>,0>>::clear(void)
0x18007b8db  lea     rdx, aLocalSprData; "'__LOCAL_SPR_DATA__'"
0x18007b8e2  lea     rcx, [rbp+0E0h+var_50]
0x18007b8e9  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18007b8ee  nop
0x18007b8ef  lea     r8, [rbp+0E0h+var_50]
0x18007b8f6  lea     rdx, [rsp+1E0h+var_1B0]
0x18007b8fb  lea     rcx, [rsp+1E0h+var_1C0]
0x18007b900  call    ??$_Try_emplace@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@$$V@?$map@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@PEAX@std@@_N@1@$$QEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::map<std::string,std::string>::_Try_emplace<std::string,>(std::string &&)
0x18007b905  mov     rdx, [rax]
0x18007b908  add     rdx, 40h ; '@'
0x18007b90c  mov     rcx, rbx
0x18007b90f  call    ?ReadFileContents@@YAJPEBGAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; ReadFileContents(ushort const *,std::string &)
0x18007b914  mov     ebx, eax
0x18007b916  lea     rcx, [rbp+0E0h+var_50]
0x18007b91d  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18007b922  test    ebx, ebx
0x18007b924  jnz     loc_18007BA44
0x18007b92a  lea     r8, [rbp+0E0h+var_70]
0x18007b92e  lea     rdx, [rsp+1E0h+var_1C0]
0x18007b933  call    ?LoadResourceWithReplace@SleepstudyJsonReporter@@CAJPEBGAEBV?$map@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@2@@std@@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@3@@Z; SleepstudyJsonReporter::LoadResourceWithReplace(ushort const *,std::map<std::string,std::string> const &,std::string &)
0x18007b938  mov     ebx, eax
0x18007b93a  test    eax, eax
0x18007b93c  jnz     loc_18007BA44
0x18007b942  lea     rcx, [rsp+1E0h+var_1C0]
0x18007b947  call    ?clear@?$_Tree@V?$_Tmap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAAXXZ; std::_Tree<std::_Tmap_traits<std::string,std::string,std::less<std::string>,std::allocator<std::pair<std::string const,std::string>>,0>>::clear(void)
0x18007b94c  lea     r8, qword_1800C8C80
0x18007b953  lea     rdx, [rsp+1E0h+var_1B0]
0x18007b958  lea     rcx, [rsp+1E0h+var_1C0]
0x18007b95d  call    ??$_Try_emplace@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@$$V@?$map@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@PEAX@std@@_N@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::map<std::string,std::string>::_Try_emplace<std::string const &,>(std::string const &)
0x18007b962  mov     rcx, [rax]
0x18007b965  add     rcx, 40h ; '@'
0x18007b969  lea     rdx, [rbp+0E0h+var_70]
0x18007b96d  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@AEBV01@@Z; std::string::operator=(std::string const &)
0x18007b972  lea     r8, qword_1800C8CA0
0x18007b979  lea     rdx, [rsp+1E0h+var_1B0]
0x18007b97e  lea     rcx, [rsp+1E0h+var_1C0]
0x18007b983  call    ??$_Try_emplace@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@$$V@?$map@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@PEAX@std@@_N@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::map<std::string,std::string>::_Try_emplace<std::string const &,>(std::string const &)
0x18007b988  mov     rdx, [rax]
0x18007b98b  add     rdx, 40h ; '@'
0x18007b98f  lea     rcx, aIdrSleepstudyT; "IDR_SLEEPSTUDY_TEMPLATE_CSS"
0x18007b996  call    ?ReadResourceContents@@YAJPEBGAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; ReadResourceContents(ushort const *,std::string &)
0x18007b99b  mov     ebx, eax
0x18007b99d  test    eax, eax
0x18007b99f  jnz     loc_18007BA44
0x18007b9a5  lea     r8, qword_1800C8CF0
0x18007b9ac  lea     rdx, [rsp+1E0h+var_1B0]
0x18007b9b1  lea     rcx, [rsp+1E0h+var_1C0]
0x18007b9b6  call    ??$_Try_emplace@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@$$V@?$map@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@PEAX@std@@_N@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::map<std::string,std::string>::_Try_emplace<std::string const &,>(std::string const &)
0x18007b9bb  mov     rdx, [rax]
0x18007b9be  add     rdx, 40h ; '@'
0x18007b9c2  lea     rcx, aIdrSleepstudyT_1; "IDR_SLEEPSTUDY_TEMPLATE_JS"
0x18007b9c9  call    ?ReadResourceContents@@YAJPEBGAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; ReadResourceContents(ushort const *,std::string &)
0x18007b9ce  mov     ebx, eax
0x18007b9d0  test    eax, eax
0x18007b9d2  jnz     short loc_18007BA44
0x18007b9d4  lea     r8, qword_1800C8CC0
0x18007b9db  lea     rdx, [rsp+1E0h+var_1B0]
0x18007b9e0  lea     rcx, [rsp+1E0h+var_1C0]
0x18007b9e5  call    ??$_Try_emplace@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@$$V@?$map@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@PEAX@std@@_N@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::map<std::string,std::string>::_Try_emplace<std::string const &,>(std::string const &)
0x18007b9ea  mov     rdx, [rax]
0x18007b9ed  add     rdx, 40h ; '@'
0x18007b9f1  lea     rcx, aIdrSleepstudyT_2; "IDR_SLEEPSTUDY_TEMPLATE_HTML"
0x18007b9f8  call    ?ReadResourceContents@@YAJPEBGAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; ReadResourceContents(ushort const *,std::string &)
0x18007b9fd  mov     ebx, eax
0x18007b9ff  test    eax, eax
0x18007ba01  jnz     short loc_18007BA44
0x18007ba03  lea     rdx, [rbp+0E0h+var_90]
0x18007ba07  lea     rcx, aIdrSleepstudyL; "IDR_SLEEPSTUDY_LOCAL_HTML"
0x18007ba0e  call    ?ReadResourceContents@@YAJPEBGAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; ReadResourceContents(ushort const *,std::string &)
0x18007ba13  mov     ebx, eax
0x18007ba15  test    eax, eax
0x18007ba17  jnz     short loc_18007BA44
0x18007ba19  mov     rdx, rdi
0x18007ba1c  lea     rcx, [rsp+1E0h+var_1A0]
0x18007ba21  call    ?open@?$basic_ofstream@DU?$char_traits@D@std@@@std@@QEAAXPEBGHH@Z; std::ofstream::open(ushort const *,int,int)
0x18007ba26  lea     rcx, [rbp+0E0h+var_90]
0x18007ba2a  cmp     [rbp+0E0h+var_78], 0Fh
0x18007ba2f  cmova   rcx, [rbp+0E0h+var_90]
0x18007ba34  lea     r8, [rsp+1E0h+var_1A0]
0x18007ba39  lea     rdx, [rsp+1E0h+var_1C0]
0x18007ba3e  call    ?StringReplaceAll@@YAXPEBDAEBV?$map@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@2@@std@@AEAV?$basic_ostream@DU?$char_traits@D@std@@@2@@Z; StringReplaceAll(char const *,std::map<std::string,std::string> const &,std::ostream &)
0x18007ba43  nop
0x18007ba44  lea     rcx, [rbp+0E0h+var_30]
0x18007ba4b  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18007ba50  nop
0x18007ba51  lea     rcx, [rsp+1E0h+var_1C0]
0x18007ba56  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::string,std::string,std::less<std::string>,std::allocator<std::pair<std::string const,std::string>>,0>>::~_Tree<std::_Tmap_traits<std::string,std::string,std::less<std::string>,std::allocator<std::pair<std::string const,std::string>>,0>>(void)
0x18007ba5b  nop
0x18007ba5c  lea     rcx, [rbp+0E0h+var_90]
0x18007ba60  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18007ba65  nop
0x18007ba66  lea     rcx, [rsp+1E0h+var_1A0]
0x18007ba6b  call    ??_D?$basic_ofstream@DU?$char_traits@D@std@@@std@@QEAAXXZ; std::ofstream::`vbase destructor'(void)
0x18007ba70  nop
0x18007ba71  lea     rcx, [rbp+0E0h+var_70]
0x18007ba75  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18007ba7a  mov     eax, ebx
0x18007ba7c  mov     rcx, [rbp+0E0h+var_10]
0x18007ba83  xor     rcx, rsp; StackCookie
0x18007ba86  call    __security_check_cookie
0x18007ba8b  lea     r11, [rsp+1E0h+var_s0]
0x18007ba93  mov     rbx, [r11+20h]
0x18007ba97  mov     rdi, [r11+28h]
0x18007ba9b  mov     rsp, r11
0x18007ba9e  pop     rbp
0x18007ba9f  retn
```
