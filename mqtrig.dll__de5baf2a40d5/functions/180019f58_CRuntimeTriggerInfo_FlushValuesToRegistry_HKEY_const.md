# CRuntimeTriggerInfo::FlushValuesToRegistry(HKEY__ * const &)

- ea: `0x180019f58`
- end: `0x18001a0d0`
- name: `?FlushValuesToRegistry@CRuntimeTriggerInfo@@AEAAXAEBQEAUHKEY__@@@Z`
- size: `376`
- prototype: `void __fastcall(CRuntimeTriggerInfo *__hidden this, HKEY *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800199a0`
- `0x18001a718`

## callees

- `0x18001519c`
- `0x1800156d4`
- `0x180019f58`

## pseudocode

```c
void __fastcall CRuntimeTriggerInfo::FlushValuesToRegistry(CRuntimeTriggerInfo *this, HKEY *a2)
{
  __int64 v3; // rax
  const wchar_t *v4; // rdx
  const wchar_t **v6; // rax
  const wchar_t *v7; // rdx
  int v8; // [rsp+20h] [rbp-30h] BYREF
  __int64 v9; // [rsp+28h] [rbp-28h]
  const wchar_t *v10; // [rsp+30h] [rbp-20h]
  int v11; // [rsp+38h] [rbp-18h]
  __int64 v12; // [rsp+40h] [rbp-10h]
  int Data; // [rsp+70h] [rbp+20h] BYREF

  v9 = 0;
  v10 = L"Name";
  v3 = (__int64)*a2;
  v4 = (const wchar_t *)*((_QWORD *)this + 261);
  v8 = 1;
  v11 = 0;
  v12 = v3;
  if ( v4 )
    v4 = *(const wchar_t **)v4;
  CmSetValue((const struct RegEntry *)&v8, v4);
  v8 = 1;
  v10 = L"Queue";
  v12 = (__int64)*a2;
  v6 = (const wchar_t **)*((_QWORD *)this + 262);
  v9 = 0;
  v11 = 0;
  if ( v6 )
    v7 = *v6;
  else
    v7 = 0;
  CmSetValue((const struct RegEntry *)&v8, v7);
  v8 = 1;
  v10 = L"Enabled";
  v12 = (__int64)*a2;
  Data = *((unsigned __int8 *)this + 2072);
  v9 = 0;
  v11 = 0;
  SetValueInternal((struct RegEntry *)&v8, 4u, (BYTE *)&Data, 4u);
  v8 = 1;
  v10 = L"Serialized";
  v12 = (__int64)*a2;
  Data = *((unsigned __int8 *)this + 2073);
  v9 = 0;
  v11 = 0;
  SetValueInternal((struct RegEntry *)&v8, 4u, (BYTE *)&Data, 4u);
  v8 = 1;
  v10 = L"MsgProcessingType";
  v12 = (__int64)*a2;
  Data = *((_DWORD *)this + 5);
  v9 = 0;
  v11 = 0;
  SetValueInternal((struct RegEntry *)&v8, 4u, (BYTE *)&Data, 4u);
}

```

## disassembly

```asm
0x180019f58  mov     [rsp-18h+arg_8], rbx
0x180019f5d  mov     [rsp-18h+arg_10], rsi
0x180019f62  push    rbp
0x180019f63  push    rdi
0x180019f64  push    r15
0x180019f66  mov     rbp, rsp
0x180019f69  sub     rsp, 50h
0x180019f6d  lea     rax, aName; "Name"
0x180019f74  mov     [rbp+var_28], 0
0x180019f7c  mov     [rbp+var_20], rax
0x180019f80  mov     rbx, rdx
0x180019f83  mov     rax, [rdx]
0x180019f86  mov     r15d, 1
0x180019f8c  mov     rdx, [rcx+828h]
0x180019f93  mov     rdi, rcx
0x180019f96  mov     [rbp+var_30], r15d
0x180019f9a  mov     [rbp+var_18], 0
0x180019fa1  mov     [rbp+var_10], rax
0x180019fa5  test    rdx, rdx
0x180019fa8  jz      short loc_180019FAD
0x180019faa  mov     rdx, [rdx]; lpData
0x180019fad  lea     rcx, [rbp+var_30]; struct RegEntry *
0x180019fb1  call    ?CmSetValue@@YAXAEBVRegEntry@@PEB_W@Z; CmSetValue(RegEntry const &,wchar_t const *)
0x180019fb6  lea     rax, aQueue; "Queue"
0x180019fbd  mov     [rbp+var_30], r15d
0x180019fc1  mov     [rbp+var_20], rax
0x180019fc5  mov     rax, [rbx]
0x180019fc8  mov     [rbp+var_10], rax
0x180019fcc  mov     rax, [rdi+830h]
0x180019fd3  mov     [rbp+var_28], 0
0x180019fdb  mov     [rbp+var_18], 0
0x180019fe2  test    rax, rax
0x180019fe5  jz      short loc_180019FEC
0x180019fe7  mov     rdx, [rax]
0x180019fea  jmp     short loc_180019FEE
0x180019fec  xor     edx, edx; lpData
0x180019fee  lea     rcx, [rbp+var_30]; struct RegEntry *
0x180019ff2  call    ?CmSetValue@@YAXAEBVRegEntry@@PEB_W@Z; CmSetValue(RegEntry const &,wchar_t const *)
0x180019ff7  lea     rax, aEnabled; "Enabled"
0x180019ffe  mov     [rbp+var_30], r15d
0x18001a002  mov     [rbp+var_20], rax
0x18001a006  lea     r8, [rbp+Data]; lpData
0x18001a00a  mov     rax, [rbx]
0x18001a00d  lea     rcx, [rbp+var_30]; struct RegEntry *
0x18001a011  mov     [rbp+var_10], rax
0x18001a015  mov     esi, 4
0x18001a01a  movzx   eax, byte ptr [rdi+818h]
0x18001a021  mov     r9d, esi; cbData
0x18001a024  mov     edx, esi; dwType
0x18001a026  mov     [rbp+Data], eax
0x18001a029  mov     [rbp+var_28], 0
0x18001a031  mov     [rbp+var_18], 0
0x18001a038  call    SetValueInternal
0x18001a03d  lea     rax, aSerialized; "Serialized"
0x18001a044  mov     [rbp+var_30], r15d
0x18001a048  mov     [rbp+var_20], rax
0x18001a04c  lea     r8, [rbp+Data]; lpData
0x18001a050  mov     rax, [rbx]
0x18001a053  lea     rcx, [rbp+var_30]; struct RegEntry *
0x18001a057  mov     [rbp+var_10], rax
0x18001a05b  mov     r9d, esi; cbData
0x18001a05e  movzx   eax, byte ptr [rdi+819h]
0x18001a065  mov     edx, esi; dwType
0x18001a067  mov     [rbp+Data], eax
0x18001a06a  mov     [rbp+var_28], 0
0x18001a072  mov     [rbp+var_18], 0
0x18001a079  call    SetValueInternal
0x18001a07e  lea     rax, aMsgprocessingt; "MsgProcessingType"
0x18001a085  mov     [rbp+var_30], r15d
0x18001a089  mov     [rbp+var_20], rax
0x18001a08d  lea     r8, [rbp+Data]; lpData
0x18001a091  mov     rax, [rbx]
0x18001a094  lea     rcx, [rbp+var_30]; struct RegEntry *
0x18001a098  mov     [rbp+var_10], rax
0x18001a09c  mov     r9d, esi; cbData
0x18001a09f  mov     eax, [rdi+14h]
0x18001a0a2  mov     edx, esi; dwType
0x18001a0a4  mov     [rbp+Data], eax
0x18001a0a7  mov     [rbp+var_28], 0
0x18001a0af  mov     [rbp+var_18], 0
0x18001a0b6  call    SetValueInternal
0x18001a0bb  lea     r11, [rsp+50h+var_s0]
0x18001a0c0  mov     rbx, [r11+28h]
0x18001a0c4  mov     rsi, [r11+30h]
0x18001a0c8  mov     rsp, r11
0x18001a0cb  pop     r15
0x18001a0cd  pop     rdi
0x18001a0ce  pop     rbp
0x18001a0cf  retn
```
