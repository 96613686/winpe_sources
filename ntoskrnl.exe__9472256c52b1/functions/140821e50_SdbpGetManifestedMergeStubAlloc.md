# SdbpGetManifestedMergeStubAlloc

- ea: `0x140821e50`
- end: `0x1408221b6`
- name: `SdbpGetManifestedMergeStubAlloc`
- size: `870`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1408221bc`

## callees

- `0x140544600`
- `0x140544740`
- `0x1406dd5c0`
- `0x1406dd640`
- `0x140821e50`
- `0x140822734`
- `0x140829278`
- `0x1408be914`
- `0x1408bf658`
- `0x1408c14bc`
- `0x1408c2f88`
- `0x140a1c030`
- `0x140acb824`

## string_xrefs

- `0x140821ee5`: `Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\SdbUpdates\ManifestedMergeStubSdbs`
- `0x140821eba`: `SdbpGetManifestedMergeStubAlloc`
- `0x140821f1c`: `SdbpGetManifestedMergeStubAlloc`
- `0x140821fe9`: `SdbpGetManifestedMergeStubAlloc`
- `0x14082217f`: `Failed to allocate stub path.`
- `0x140822164`: `Failed to duplicate stub path.`
- `0x14082213f`: `Failed to allocate or convert stub path.`
- `0x140821f0b`: `AslRegistryGetKey failed to open ManifestedMergeStubSdbs key [%x]`

## pseudocode

```c
__int64 __fastcall SdbpGetManifestedMergeStubAlloc(_QWORD *a1, const wchar_t *a2)
{
  ULONG v2; // r12d
  __int64 v5; // r15
  wchar_t *v6; // r13
  HANDLE v7; // rcx
  NTSTATUS MergeSdbsDisabled; // ebx
  int Key; // eax
  unsigned int v10; // ebx
  __int64 v11; // rcx
  __int64 v12; // rsi
  __int64 v13; // rax
  ULONG v14; // ebx
  const char *v15; // r9
  int v16; // r8d
  NTSTATUS v17; // eax
  __int64 v18; // rax
  ULONG v19; // ebx
  unsigned __int64 v20; // r14
  __int64 v21; // rdx
  __int64 v22; // rcx
  __int64 v23; // r8
  __int64 v24; // r9
  const wchar_t *NtSystemRoot; // rax
  const wchar_t *v26; // rbx
  size_t v27; // r8
  __int64 v28; // rax
  ULONG Length; // [rsp+20h] [rbp-20h]
  PULONG ResultLength; // [rsp+28h] [rbp-18h]
  __int64 v31; // [rsp+30h] [rbp-10h] BYREF
  HANDLE Handle; // [rsp+38h] [rbp-8h] BYREF
  ULONG v34; // [rsp+90h] [rbp+50h] BYREF
  ULONG v35; // [rsp+98h] [rbp+58h] BYREF

  v2 = 0;
  v35 = 0;
  v34 = 0;
  v31 = 0;
  Handle = 0;
  if ( !a1 )
    return 3221225711LL;
  *a1 = 0;
  v5 = 0;
  v6 = 0;
  MergeSdbsDisabled = SdbpGetMergeSdbsDisabled(&v35);
  if ( MergeSdbsDisabled >= 0 )
  {
    if ( v35 )
    {
      MergeSdbsDisabled = -1073741772;
    }
    else
    {
      Key = AslRegistryGetKey(
              &Handle,
              L"Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\SdbUpdates\\ManifestedMergeStubSdbs",
              2147483904LL,
              1);
      MergeSdbsDisabled = Key;
      if ( Key >= 0 )
      {
        v10 = 1;
        while ( wcsicmp(a2, (const wchar_t *)qword_14000AEC8[4 * v10]) )
        {
          if ( (int)++v10 >= 10 )
          {
LABEL_13:
            MergeSdbsDisabled = -1073741772;
            goto LABEL_14;
          }
        }
        v12 = -1;
        v13 = -1;
        do
          ++v13;
        while ( a2[v13] );
        v14 = 2 * v13 + 18;
        v35 = v14;
        v5 = AslAlloc(v11, v14);
        if ( v5 )
        {
          while ( 1 )
          {
            v17 = ZwEnumerateValueKey(Handle, v2, KeyValuePartialInformation, (PVOID)v5, v14, &v34);
            MergeSdbsDisabled = v17;
            if ( v17 != -2147483643 && v17 != -1073741789 )
            {
              if ( v17 == -2147483622 )
                goto LABEL_13;
              if ( v17 < 0 )
              {
                v15 = "Failed to query partial info.";
                v16 = 1239;
                goto LABEL_28;
              }
              if ( *(_DWORD *)(v5 + 4) == 1 && !wcsicmp(a2, (const wchar_t *)(v5 + 12)) )
                break;
            }
            v14 = v35;
            ++v2;
          }
          v18 = -1;
          do
            ++v18;
          while ( a2[v18] );
          v19 = 2 * v18 + 538;
          v20 = v19;
          v6 = (wchar_t *)AslAlloc(0, v19);
          if ( !v6 )
          {
            v15 = "Failed to allocate basic info.";
            v16 = 1256;
            goto LABEL_27;
          }
          MergeSdbsDisabled = ZwEnumerateValueKey(Handle, v2, KeyValueBasicInformation, v6, v19, &v34);
          if ( MergeSdbsDisabled < 0 )
          {
            v15 = "Failed to query basic info.";
            v16 = 1267;
            goto LABEL_28;
          }
          if ( (unsigned __int64)v34 + 2 > v20 )
          {
            MergeSdbsDisabled = -1073741789;
            v15 = "Buffer too small to query basic info.";
            v16 = 1272;
            goto LABEL_28;
          }
          NtSystemRoot = (const wchar_t *)RtlGetNtSystemRoot(v22, v21, v23, v24, Length, ResultLength, v31);
          v26 = NtSystemRoot;
          v27 = -1;
          do
            ++v27;
          while ( NtSystemRoot[v27] );
          if ( wcsnicmp(NtSystemRoot, v6 + 6, v27) )
          {
            MergeSdbsDisabled = AslStringDuplicate(&v31, v6 + 6);
            if ( MergeSdbsDisabled < 0 )
            {
              v15 = "Failed to duplicate stub path.";
              v16 = 1299;
              goto LABEL_28;
            }
          }
          else
          {
            do
              ++v12;
            while ( v26[v12] );
            MergeSdbsDisabled = AslPathToSystemPath(&v31, &v6[v12 + 6]);
            if ( MergeSdbsDisabled < 0 )
            {
              v15 = "Failed to allocate or convert stub path.";
              v16 = 1292;
              goto LABEL_28;
            }
          }
          v28 = v31;
          if ( !v31 )
          {
            v15 = "Failed to allocate stub path.";
            v16 = 1306;
            goto LABEL_27;
          }
          MergeSdbsDisabled = 0;
          v31 = 0;
          *a1 = v28;
        }
        else
        {
          v15 = "Failed to allocate partial info.";
          v16 = 1220;
LABEL_27:
          MergeSdbsDisabled = -1073741801;
LABEL_28:
          AslLogCallPrintf(1, (unsigned int)"SdbpGetManifestedMergeStubAlloc", v16, (_DWORD)v15);
        }
      }
      else if ( Key != -1073741772 )
      {
        AslLogCallPrintf(
          1,
          (unsigned int)"SdbpGetManifestedMergeStubAlloc",
          1200,
          (unsigned int)"AslRegistryGetKey failed to open ManifestedMergeStubSdbs key [%x]");
      }
LABEL_14:
      v7 = Handle;
      if ( (char *)Handle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        ZwClose(Handle);
    }
  }
  else
  {
    AslLogCallPrintf(
      1,
      (unsigned int)"SdbpGetManifestedMergeStubAlloc",
      1184,
      (unsigned int)"SdbpGetMergeSdbsDisabled failed [%x]");
  }
  if ( v31 )
    AslFree(v7, v31);
  if ( v5 )
    AslFree(v7, v5);
  if ( v6 )
    AslFree(v7, v6);
  return (unsigned int)MergeSdbsDisabled;
}

```

## disassembly

```asm
0x140821e50  mov     [rsp-38h+arg_8], rbx
0x140821e55  mov     [rsp-38h+arg_0], rcx
0x140821e5a  push    rbp
0x140821e5b  push    rsi
0x140821e5c  push    rdi
0x140821e5d  push    r12
0x140821e5f  push    r13
0x140821e61  push    r14
0x140821e63  push    r15
0x140821e65  mov     rbp, rsp
0x140821e68  sub     rsp, 40h
0x140821e6c  xor     r12d, r12d
0x140821e6f  mov     r14, rdx
0x140821e72  mov     [rbp+arg_18], r12d
0x140821e76  mov     [rbp+arg_10], r12d
0x140821e7a  mov     [rbp+var_10], r12
0x140821e7e  mov     [rbp+Handle], r12
0x140821e82  test    rcx, rcx
0x140821e85  jnz     short loc_140821E91
0x140821e87  mov     eax, 0C00000EFh
0x140821e8c  jmp     loc_140821F94
0x140821e91  mov     [rcx], r12
0x140821e94  mov     r15, r12
0x140821e97  lea     rcx, [rbp+arg_18]
0x140821e9b  mov     r13, r12
0x140821e9e  call    SdbpGetMergeSdbsDisabled
0x140821ea3  mov     ebx, eax
0x140821ea5  test    eax, eax
0x140821ea7  jns     short loc_140821ED0
0x140821ea9  lea     r9, aSdbpgetmergesd; "SdbpGetMergeSdbsDisabled failed [%x]"
0x140821eb0  mov     [rsp+40h+Length], eax
0x140821eb4  mov     r8d, 4A0h
0x140821eba  lea     rdx, aSdbpgetmanifes; "SdbpGetManifestedMergeStubAlloc"
0x140821ec1  mov     ecx, 1
0x140821ec6  call    AslLogCallPrintf
0x140821ecb  jmp     loc_140821F6A
0x140821ed0  cmp     [rbp+arg_18], r12d
0x140821ed4  jz      short loc_140821EE0
0x140821ed6  mov     ebx, 0C0000034h
0x140821edb  jmp     loc_140821F6A
0x140821ee0  mov     edi, 1
0x140821ee5  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows NT\\Curren"...
0x140821eec  mov     r9d, edi
0x140821eef  lea     rcx, [rbp+Handle]
0x140821ef3  mov     r8d, 80000100h
0x140821ef9  call    AslRegistryGetKey
0x140821efe  mov     ebx, eax
0x140821f00  test    eax, eax
0x140821f02  jns     short loc_140821F2C
0x140821f04  cmp     eax, 0C0000034h
0x140821f09  jz      short loc_140821F57
0x140821f0b  lea     r9, aAslregistryget_3; "AslRegistryGetKey failed to open Manife"...
0x140821f12  mov     [rsp+40h+Length], eax
0x140821f16  mov     r8d, 4B0h
0x140821f1c  lea     rdx, aSdbpgetmanifes; "SdbpGetManifestedMergeStubAlloc"
0x140821f23  mov     ecx, edi
0x140821f25  call    AslLogCallPrintf
0x140821f2a  jmp     short loc_140821F57
0x140821f2c  mov     ebx, edi
0x140821f2e  lea     rax, qword_14000AEC8
0x140821f35  mov     edx, ebx
0x140821f37  shl     rdx, 5
0x140821f3b  mov     rcx, r14; Str1
0x140821f3e  mov     rdx, [rdx+rax]; Str2
0x140821f42  call    _wcsicmp
0x140821f47  test    eax, eax
0x140821f49  jz      short loc_140821FAD
0x140821f4b  add     ebx, edi
0x140821f4d  cmp     ebx, 0Ah
0x140821f50  jl      short loc_140821F2E
0x140821f52  mov     ebx, 0C0000034h
0x140821f57  mov     rcx, [rbp+Handle]; Handle
0x140821f5b  lea     rax, [rcx-1]
0x140821f5f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140821f63  ja      short loc_140821F6A
0x140821f65  call    ZwClose
0x140821f6a  mov     rdx, [rbp+var_10]
0x140821f6e  test    rdx, rdx
0x140821f71  jz      short loc_140821F78
0x140821f73  call    AslFree
0x140821f78  test    r15, r15
0x140821f7b  jz      short loc_140821F85
0x140821f7d  mov     rdx, r15
0x140821f80  call    AslFree
0x140821f85  test    r13, r13
0x140821f88  jz      short loc_140821F92
0x140821f8a  mov     rdx, r13
0x140821f8d  call    AslFree
0x140821f92  mov     eax, ebx
0x140821f94  mov     rbx, [rsp+40h+arg_8]
0x140821f9c  add     rsp, 40h
0x140821fa0  pop     r15
0x140821fa2  pop     r14
0x140821fa4  pop     r13
0x140821fa6  pop     r12
0x140821fa8  pop     rdi
0x140821fa9  pop     rsi
0x140821faa  pop     rbp
0x140821fab  retn
0x140821fad  or      rsi, 0FFFFFFFFFFFFFFFFh
0x140821fb1  mov     rax, rsi
0x140821fb4  inc     rax
0x140821fb7  cmp     [r14+rax*2], r12w
0x140821fbc  jnz     short loc_140821FB4
0x140821fbe  lea     ebx, ds:12h[rax*2]
0x140821fc5  mov     edx, ebx
0x140821fc7  mov     [rbp+arg_18], ebx
0x140821fca  call    AslAlloc
0x140821fcf  mov     r15, rax
0x140821fd2  test    rax, rax
0x140821fd5  jnz     short loc_140821FFC
0x140821fd7  lea     r9, aFailedToAlloca_1; "Failed to allocate partial info."
0x140821fde  mov     r8d, 4C4h
0x140821fe4  mov     ebx, 0C0000017h
0x140821fe9  lea     rdx, aSdbpgetmanifes; "SdbpGetManifestedMergeStubAlloc"
0x140821ff0  mov     ecx, edi
0x140821ff2  call    AslLogCallPrintf
0x140821ff7  jmp     loc_140821F57
0x140821ffc  mov     rcx, [rbp+Handle]; KeyHandle
0x140822000  lea     rax, [rbp+arg_10]
0x140822004  mov     [rsp+40h+ResultLength], rax; ResultLength
0x140822009  mov     r9, r15; KeyValueInformation
0x14082200c  mov     r8d, 2; KeyValueInformationClass
0x140822012  mov     [rsp+40h+Length], ebx; Length
0x140822016  mov     edx, r12d; Index
0x140822019  call    ZwEnumerateValueKey
0x14082201e  mov     ebx, eax
0x140822020  cmp     eax, 80000005h
0x140822025  jz      short loc_140822059
0x140822027  cmp     eax, 0C0000023h
0x14082202c  jz      short loc_140822059
0x14082202e  cmp     eax, 8000001Ah
0x140822033  jz      loc_140821F52
0x140822039  test    eax, eax
0x14082203b  js      loc_1408221A4
0x140822041  cmp     [r15+4], edi
0x140822045  jnz     short loc_140822059
0x140822047  lea     rdx, [r15+0Ch]; Str2
0x14082204b  mov     rcx, r14; Str1
0x14082204e  call    _wcsicmp
0x140822053  xor     ecx, ecx
0x140822055  test    eax, eax
0x140822057  jz      short loc_140822061
0x140822059  mov     ebx, [rbp+arg_18]
0x14082205c  add     r12d, edi
0x14082205f  jmp     short loc_140821FFC
0x140822061  mov     rax, rsi
0x140822064  inc     rax
0x140822067  cmp     [r14+rax*2], cx
0x14082206c  jnz     short loc_140822064
0x14082206e  lea     ebx, ds:21Ah[rax*2]
0x140822075  mov     edx, ebx
0x140822077  mov     r14d, ebx
0x14082207a  call    AslAlloc
0x14082207f  mov     r13, rax
0x140822082  test    rax, rax
0x140822085  jnz     short loc_140822099
0x140822087  lea     r9, aFailedToAlloca_6; "Failed to allocate basic info."
0x14082208e  mov     r8d, 4E8h
0x140822094  jmp     loc_140821FE4
0x140822099  mov     rcx, [rbp+Handle]; KeyHandle
0x14082209d  lea     rax, [rbp+arg_10]
0x1408220a1  mov     [rsp+40h+ResultLength], rax; ResultLength
0x1408220a6  mov     r9, r13; KeyValueInformation
0x1408220a9  xor     r8d, r8d; KeyValueInformationClass
0x1408220ac  mov     [rsp+40h+Length], ebx; Length
0x1408220b0  mov     edx, r12d; Index
0x1408220b3  call    ZwEnumerateValueKey
0x1408220b8  xor     r12d, r12d
0x1408220bb  mov     ebx, eax
0x1408220bd  test    eax, eax
0x1408220bf  jns     short loc_1408220D3
0x1408220c1  lea     r9, aFailedToQueryB_0; "Failed to query basic info."
0x1408220c8  mov     r8d, 4F3h
0x1408220ce  jmp     loc_140821FE9
0x1408220d3  mov     eax, [rbp+arg_10]
0x1408220d6  add     rax, 2
0x1408220da  cmp     rax, r14
0x1408220dd  jbe     short loc_1408220F6
0x1408220df  mov     ebx, 0C0000023h
0x1408220e4  lea     r9, aBufferTooSmall_0; "Buffer too small to query basic info."
0x1408220eb  mov     r8d, 4F8h
0x1408220f1  jmp     loc_140821FE9
0x1408220f6  call    RtlGetNtSystemRoot
0x1408220fb  mov     rbx, rax
0x1408220fe  mov     r8, rsi
0x140822101  inc     r8; MaxCount
0x140822104  cmp     [rax+r8*2], r12w
0x140822109  jnz     short loc_140822101
0x14082210b  lea     rdx, [r13+0Ch]; Str2
0x14082210f  mov     rcx, rbx; Str1
0x140822112  call    _wcsnicmp
0x140822117  test    eax, eax
0x140822119  jnz     short loc_140822151
0x14082211b  inc     rsi
0x14082211e  cmp     [rbx+rsi*2], r12w
0x140822123  jnz     short loc_14082211B
0x140822125  lea     rdx, ds:0Ch[rsi*2]
0x14082212d  add     rdx, r13
0x140822130  lea     rcx, [rbp+var_10]
0x140822134  call    AslPathToSystemPath
0x140822139  mov     ebx, eax
0x14082213b  test    eax, eax
0x14082213d  jns     short loc_140822176
0x14082213f  lea     r9, aFailedToAlloca_2; "Failed to allocate or convert stub path"...
0x140822146  mov     r8d, 50Ch
0x14082214c  jmp     loc_140821FE9
0x140822151  lea     rdx, [r13+0Ch]
0x140822155  lea     rcx, [rbp+var_10]
0x140822159  call    AslStringDuplicate
0x14082215e  mov     ebx, eax
0x140822160  test    eax, eax
0x140822162  jns     short loc_140822176
0x140822164  lea     r9, aFailedToDuplic; "Failed to duplicate stub path."
0x14082216b  mov     r8d, 513h
0x140822171  jmp     loc_140821FE9
0x140822176  mov     rax, [rbp+var_10]
0x14082217a  test    rax, rax
0x14082217d  jnz     short loc_140822191
0x14082217f  lea     r9, aFailedToAlloca_10; "Failed to allocate stub path."
0x140822186  mov     r8d, 51Ah
0x14082218c  jmp     loc_140821FE4
0x140822191  mov     rcx, [rbp+arg_0]
0x140822195  mov     ebx, r12d
0x140822198  mov     [rbp+var_10], r12
0x14082219c  mov     [rcx], rax
0x14082219f  jmp     loc_140821F57
0x1408221a4  lea     r9, aFailedToQueryP; "Failed to query partial info."
0x1408221ab  mov     r8d, 4D7h
0x1408221b1  jmp     loc_140821FE9
```
