# JsonReader::PushToStack(JsonValue *)

- ea: `0x1400245d4`
- end: `0x14002469c`
- name: `?PushToStack@JsonReader@@AEAAXPEAVJsonValue@@@Z`
- size: `200`
- prototype: `void __fastcall(JsonReader *__hidden this, struct JsonValue *)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1400239a4`
- `0x140023b80`
- `0x140023e64`

## callees

- `0x1400017d4`
- `0x14001c78c`
- `0x1400245d4`
- `0x1400246a4`
- `0x14002c3e8`

## pseudocode

```c
void __fastcall JsonReader::PushToStack(JsonReader *this, struct JsonValue *a2)
{
  unsigned __int64 v4; // rcx
  __int64 v5; // rdx
  unsigned __int64 v6; // rdi
  __int64 v7; // rsi
  _BYTE pExceptionObject[56]; // [rsp+20h] [rbp-38h] BYREF

  v4 = *((_QWORD *)this + 4);
  if ( v4 >= 0xA )
  {
    JsonException::JsonException((JsonException *)pExceptionObject, -895418330);
    throw (JsonException *)pExceptionObject;
  }
  if ( ((*((_BYTE *)this + 24) + (_BYTE)v4) & 1) == 0 && *((_QWORD *)this + 2) <= (v4 + 2) >> 1 )
    std::deque<JsonValue *>::_Growmap(this);
  v5 = *((_QWORD *)this + 2);
  *((_QWORD *)this + 3) &= 2 * v5 - 1;
  v6 = *((_QWORD *)this + 4) + *((_QWORD *)this + 3);
  v7 = (v6 >> 1) & (v5 - 1);
  if ( !*(_QWORD *)(*((_QWORD *)this + 1) + 8 * v7) )
    *(_QWORD *)(*((_QWORD *)this + 1) + 8 * v7) = operator new(0x10u);
  *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 1) + 8 * ((v6 >> 1) & (*((_QWORD *)this + 2) - 1LL))) + 8 * (v6 & 1)) = a2;
  ++*((_QWORD *)this + 4);
}

```

## disassembly

```asm
0x1400245d4  push    rbx
0x1400245d6  push    rbp
0x1400245d7  push    rsi
0x1400245d8  push    rdi
0x1400245d9  push    r14
0x1400245db  sub     rsp, 30h
0x1400245df  mov     rbx, rcx
0x1400245e2  mov     r14, rdx
0x1400245e5  mov     rcx, [rcx+20h]
0x1400245e9  cmp     rcx, 0Ah
0x1400245ed  jnb     loc_14002467B
0x1400245f3  mov     al, cl
0x1400245f5  add     al, [rbx+18h]
0x1400245f8  test    al, 1
0x1400245fa  jnz     short loc_140024611
0x1400245fc  lea     rax, [rcx+2]
0x140024600  shr     rax, 1
0x140024603  cmp     [rbx+10h], rax
0x140024607  ja      short loc_140024611
0x140024609  mov     rcx, rbx
0x14002460c  call    ?_Growmap@?$deque@PEAVJsonValue@@V?$allocator@PEAVJsonValue@@@std@@@std@@AEAAX_K@Z; std::deque<JsonValue *>::_Growmap(unsigned __int64)
0x140024611  mov     rdx, [rbx+10h]
0x140024615  lea     rax, ds:0FFFFFFFFFFFFFFFFh[rdx*2]
0x14002461d  and     [rbx+18h], rax
0x140024621  lea     rsi, [rdx-1]
0x140024625  mov     rdi, [rbx+18h]
0x140024629  add     rdi, [rbx+20h]
0x14002462d  mov     rax, [rbx+8]
0x140024631  mov     rbp, rdi
0x140024634  shr     rbp, 1
0x140024637  and     rsi, rbp
0x14002463a  cmp     qword ptr [rax+rsi*8], 0
0x14002463f  jnz     short loc_140024653
0x140024641  mov     ecx, 10h; Size
0x140024646  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14002464b  mov     rcx, [rbx+8]
0x14002464f  mov     [rcx+rsi*8], rax
0x140024653  mov     rcx, [rbx+10h]
0x140024657  and     edi, 1
0x14002465a  mov     rax, [rbx+8]
0x14002465e  dec     rcx
0x140024661  and     rcx, rbp
0x140024664  mov     rax, [rax+rcx*8]
0x140024668  mov     [rax+rdi*8], r14
0x14002466c  inc     qword ptr [rbx+20h]
0x140024670  add     rsp, 30h
0x140024674  pop     r14
0x140024676  pop     rdi
0x140024677  pop     rsi
0x140024678  pop     rbp
0x140024679  pop     rbx
0x14002467a  retn
0x14002467b  mov     edx, 0CAA10026h; int
0x140024680  lea     rcx, [rsp+58h+pExceptionObject]; this
0x140024685  call    ??0JsonException@@QEAA@J@Z; JsonException::JsonException(long)
0x14002468a  lea     rdx, _TI2?AVJsonException@@; pThrowInfo
0x140024691  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x140024696  call    _CxxThrowException_0
```
