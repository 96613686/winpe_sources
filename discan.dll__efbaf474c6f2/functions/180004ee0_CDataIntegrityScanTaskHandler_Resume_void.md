# CDataIntegrityScanTaskHandler::Resume(void)

- ea: `0x180004ee0`
- end: `0x180004fce`
- name: `?Resume@CDataIntegrityScanTaskHandler@@UEAAJXZ`
- size: `238`
- prototype: `__int64 __fastcall(CDataIntegrityScanTaskHandler *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1800032f8`
- `0x180004ee0`
- `0x180006470`
- `0x180006688`

## string_xrefs

- `0x180004eee`: `CDataIntegrityScanTaskHandler::Resume`

## pseudocode

```c
__int64 __fastcall CDataIntegrityScanTaskHandler::Resume(CDataIntegrityScanTaskHandler *this)
{
  _QWORD *ThreadLocalStoragePointer; // rax
  __int64 v2; // rdx
  PVOID *v3; // rcx
  const char *v5; // [rsp+40h] [rbp-18h] BYREF
  int v6; // [rsp+48h] [rbp-10h]

  ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
  v5 = "CDataIntegrityScanTaskHandler::Resume";
  v2 = ThreadLocalStoragePointer[tls_index];
  ++*(_WORD *)(v2 + 8);
  *(_QWORD *)(v2 + 16) = "CDataIntegrityScanTaskHandler::Resume";
  v3 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_aZs(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)"CDataIntegrityScanTaskHandler::Resume");
      v3 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v3 != &WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 1) != 0 && *((_BYTE *)v3 + 25) >= 4u )
      WPP_SF_(v3[2], 37, &WPP_a6ebff40181d3a1f9fe9a55f66516085_Traceguids);
  }
  v6 = 0;
  CHResultImp::~CHResultImp((CHResultImp *)&v5);
  return 0;
}

```

## disassembly

```asm
0x180004ee0  mov     r11, rsp
0x180004ee3  push    rbx
0x180004ee4  sub     rsp, 50h
0x180004ee8  mov     ecx, cs:_tls_index
0x180004eee  lea     r9, aCdataintegrity; "CDataIntegrityScanTaskHandler::Resume"
0x180004ef5  mov     rax, gs:58h
0x180004efe  mov     r8d, 8
0x180004f04  mov     [r11-18h], r9
0x180004f08  mov     rdx, [rax+rcx*8]
0x180004f0c  movzx   ecx, cs:?GlobalIndentString@@3U_STRING@@A; _STRING GlobalIndentString
0x180004f13  mov     eax, 10h
0x180004f18  inc     word ptr [r8+rdx]
0x180004f1d  movzx   r8d, word ptr [r8+rdx]
0x180004f22  mov     [rax+rdx], r9
0x180004f26  cmp     r8w, cx
0x180004f2a  movzx   eax, cx
0x180004f2d  cmovb   ax, r8w
0x180004f32  cmovb   cx, r8w
0x180004f37  mov     [rsp+58h+var_28], ax
0x180004f3c  xor     eax, eax
0x180004f3e  mov     [rsp+58h+var_24], eax
0x180004f42  mov     rax, cs:off_180047060; "                                       "...
0x180004f49  mov     [rsp+58h+var_26], cx
0x180004f4e  mov     [r11-20h], rax
0x180004f52  mov     rcx, cs:WPP_GLOBAL_Control
0x180004f59  lea     rbx, WPP_GLOBAL_Control
0x180004f60  cmp     rcx, rbx
0x180004f63  jz      short loc_180004FB4
0x180004f65  test    byte ptr [rcx+1Ch], 1
0x180004f69  jz      short loc_180004F8E
0x180004f6b  cmp     byte ptr [rcx+19h], 5
0x180004f6f  jb      short loc_180004F8E
0x180004f71  mov     rcx, [rcx+10h]; LoggerHandle
0x180004f75  mov     edx, 0Dh
0x180004f7a  mov     [r11-38h], r9
0x180004f7e  lea     r9, [r11-28h]
0x180004f82  call    WPP_SF_aZs
0x180004f87  mov     rcx, cs:WPP_GLOBAL_Control
0x180004f8e  cmp     rcx, rbx
0x180004f91  jz      short loc_180004FB4
0x180004f93  test    byte ptr [rcx+1Ch], 1
0x180004f97  jz      short loc_180004FB4
0x180004f99  cmp     byte ptr [rcx+19h], 4
0x180004f9d  jb      short loc_180004FB4
0x180004f9f  mov     rcx, [rcx+10h]
0x180004fa3  lea     r8, WPP_a6ebff40181d3a1f9fe9a55f66516085_Traceguids
0x180004faa  mov     edx, 25h ; '%'
0x180004faf  call    WPP_SF_
0x180004fb4  lea     rcx, [rsp+58h+var_18]; this
0x180004fb9  mov     [rsp+58h+var_10], 0
0x180004fc1  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x180004fc6  xor     eax, eax
0x180004fc8  add     rsp, 50h
0x180004fcc  pop     rbx
0x180004fcd  retn
```
