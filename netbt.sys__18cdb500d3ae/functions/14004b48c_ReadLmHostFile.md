# ReadLmHostFile

- ea: `0x14004b48c`
- end: `0x14004b555`
- name: `ReadLmHostFile`
- size: `201`
- prototype: `void __fastcall(__int64, char *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14004abd4`

## callees

- `0x140043b4c`
- `0x14004b48c`
- `0x14004b55c`

## import_xrefs

- `ntoskrnl!strrchr` at `0x14004b4da`
- `ntoskrnl!strrchr` at `0x14004b4da`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004b50f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004b52c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004b50f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004b52c`

## pseudocode

```c
void __fastcall ReadLmHostFile(__int64 a1, char *a2)
{
  void *v2; // rdi
  char *v3; // rbx
  char *v4; // rax
  char *Str; // [rsp+38h] [rbp+10h] BYREF

  Str = a2;
  dword_140039658 = 0;
  v2 = *(void **)(a1 + 528);
  Str = 0;
  Src = 0;
  if ( (int)NTGetLmHostPath(&Str) >= 0 )
  {
    v3 = Str;
    v4 = strrchr(Str, 92);
    if ( v4 )
    {
      Src = v3;
      dword_140039658 = (_DWORD)v4 - (_DWORD)v3 + 1;
      if ( (BYTE3(xmmword_140038420) & 2) != 0 )
        WPP_SF_s(1049, 10, WPP_4415eb54eeae398ca87ebea1335945fe_Traceguids, v3);
    }
    else
    {
      ExFreePoolWithTag(v3, 0);
    }
  }
  if ( v2 )
    ExFreePoolWithTag(v2, 0);
}

```

## disassembly

```asm
0x14004b48c  mov     rax, rsp
0x14004b48f  mov     [rax+8], rbx
0x14004b493  mov     [rax+10h], rdx
0x14004b497  push    rdi
0x14004b498  sub     rsp, 20h
0x14004b49c  mov     cs:dword_140039658, 0
0x14004b4a6  mov     rdi, [rcx+210h]
0x14004b4ad  lea     rcx, [rax+10h]
0x14004b4b1  mov     qword ptr [rax+10h], 0
0x14004b4b9  mov     cs:Src, 0
0x14004b4c4  call    NTGetLmHostPath
0x14004b4c9  test    eax, eax
0x14004b4cb  js      short loc_14004B505
0x14004b4cd  mov     rbx, [rsp+28h+Str]
0x14004b4d2  mov     edx, 5Ch ; '\'; Ch
0x14004b4d7  mov     rcx, rbx; Str
0x14004b4da  call    cs:__imp_strrchr
0x14004b4e1  nop     dword ptr [rax+rax+00h]
0x14004b4e6  test    rax, rax
0x14004b4e9  jz      short loc_14004B527
0x14004b4eb  sub     eax, ebx
0x14004b4ed  mov     cs:Src, rbx
0x14004b4f4  inc     eax
0x14004b4f6  mov     cs:dword_140039658, eax
0x14004b4fc  test    byte ptr cs:xmmword_140038420+3, 2
0x14004b503  jnz     short loc_14004B53A
0x14004b505  test    rdi, rdi
0x14004b508  jz      short loc_14004B51B
0x14004b50a  xor     edx, edx; Tag
0x14004b50c  mov     rcx, rdi; P
0x14004b50f  call    cs:__imp_ExFreePoolWithTag
0x14004b516  nop     dword ptr [rax+rax+00h]
0x14004b51b  mov     rbx, [rsp+28h+arg_0]
0x14004b520  add     rsp, 20h
0x14004b524  pop     rdi
0x14004b525  retn
0x14004b527  xor     edx, edx; Tag
0x14004b529  mov     rcx, rbx; P
0x14004b52c  call    cs:__imp_ExFreePoolWithTag
0x14004b533  nop     dword ptr [rax+rax+00h]
0x14004b538  jmp     short loc_14004B505
0x14004b53a  mov     edx, 0Ah
0x14004b53f  lea     r8, WPP_4415eb54eeae398ca87ebea1335945fe_Traceguids
0x14004b546  mov     ecx, 419h
0x14004b54b  mov     r9, rbx
0x14004b54e  call    WPP_SF_s
0x14004b553  jmp     short loc_14004B505
```
